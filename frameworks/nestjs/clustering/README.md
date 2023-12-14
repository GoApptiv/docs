# NestJS Project with Clustering

## Overview

This repository demonstrates how to implement clustering in a NestJS project to improve performance and handle concurrent requests efficiently. Clustering allows the application to utilize multiple CPU cores, distributing the workload among them.

## Getting Started

Follow these steps to integrate clustering into your NestJS project:

### 1. Create Clustering Configuration

Create a file named `app-cluster.service.ts` in the `src` directory with the following content:

```typescript
// src/app-cluster.service.ts

import cluster from "node:cluster";
import * as os from "os";
import { Injectable } from "@nestjs/common";

const numCPUs = os.cpus().length;

@Injectable()
export class AppClusterService {
  static clusterize(callback: any): void {
    if (cluster.isPrimary) {
      console.info(`Master server started on ${process.pid}`);
      for (let i = 0; i < numCPUs; i++) {
        cluster.fork();
      }
      cluster.on("exit", (worker, code, signal) => {
        console.info(
          `Worker ${worker.process.pid} died. Restarting`,
          code,
          signal
        );
        cluster.fork();
      });
    } else {
      console.info(`Cluster server started on ${process.pid}`);
      callback();
    }
  }
}
```

### 2. Update TypeScript Configuration

Add `"esModuleInterop": true` to your `tsconfig.json` file:

```json
{
  "compilerOptions": {
    "esModuleInterop": true
    // other options...
  }
  // other configurations...
}
```

### 3. Update Main Application File

In your `src/main.ts` file, use `AppClusterService.clusterize(bootstrap)` instead of simply calling `bootstrap`:

```typescript
// src/main.ts

import { NestFactory } from "@nestjs/core";
import { AppModule } from "./app.module";
import { AppClusterService } from "./app-cluster.service";

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}

AppClusterService.clusterize(bootstrap);
```

## Running the Application

Start your NestJS application with clustering enabled:

```bash
npm start
```

This will launch the application in clustered mode, utilizing multiple CPU cores.

Feel free to customize the number of forks and other clustering settings based on your application's requirements.
