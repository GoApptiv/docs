
# ReactJS - Standards

## Introduction

This guide helps new developers understand the React code style and best practices we follow here in [GoApptiv](https://www.goapptiv.com)



![SLACK](data:image/png;base64,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)
[This channel](https://goapptiv.slack.com/archives/C03ATGM9AF7) is a great place to find out about current UI practices, ask questions, chat and help other developers who might need assistance. If you have any new idea or interesting approach, this is a great forum to discuss and get some feedback.

 - [Installation](#installation)
    -  [Project Creation ](#project-creation)
    -  [Linting Configuration ](#linting-configuration)
 - [Project Structure]
 - [Basic Rules](#basic-rules)
 - [Naming Conventions](#naming-conventions)
    - [File Extensions](#file-extensions)
    - [File Name and Components](#file-name-and-components)
    - [Import and Referencing](#import-and-referencing)
    - [State and Variables](#state-and-variables)  
    - [Event Names and Handlers](#event-names-and-handlers) 


# Installation
# Project Creation
We use project generator [create-react-app](https://create-react-app.dev/) as it saves a lot of boilerplate work and provides build setup.

We higly recommend using [typescript](https://www.typescriptlang.org/) in your project.

Creating a new reactjs project using create-react-app with typescript template.
```bash
  npx create-react-app app-name --template typescript
```

# Linting Configuration
[eslint](https://eslint.org/docs/user-guide/getting-started)


# Basic Rules

- Include only one react component per file.
- Always use TSX syntax.


# Naming Conventions
# File Extensions
Use .tsx when we embedd and return JSX elements.

Use .ts for plain typescript files.

# File Name and Components
- File and Component name need to be identical.
- Use PascalCase naming convention for filename as well as component name.

```bash
// Bad (Filename and component name are not same)
Filename: namingConvention.tsx
Filename: naming_convention.tsx
Filename: naming-convention.tsx

const NamingConvention: React.FC<Props> = ({}) => { }
```

```bash
// Good (Filename and component name are same)
Filename: NamingConvention.tsx

const NamingConvention: React.FC<Props> = ({}) => { }
```


# Import And Referencing

- Use PascalCase for importing react components.
```bash
// Bad (not PascalCase)
import namingConvention from './NamingConvention';

// Good
import NamingConvention from './NamingConvention';
```


- Use CamelCase for referencing react instances.
```bash
// Bad (not CamelCase)
const NamingConvention = <NamingConvention />;

// Good
const namingConvention = <NamingConvention />;
```

# State and Variables

- Use CamelCase for state, variables and setter functions
```bash
// Bad (not CamelCase)
const [namingconventions,setnamingconventions] = useState([]);

// Good
const [namingConventions,setNamingConventions] = useState([]);
```

# Event Names and Handlers
Use consistent name for events and its handlers.
Event handlers: These are methods that triggered after an event.

Event handlers should:
- begin with 'handle'
- end with the name of the event they handle (eg, Click, Change)
- be present-tense
- should be CamelCase

```bash
// Bad (past tense, did not begin with handle )
<input name="firstName" onChange={firstNameChanged} />

// Good
<input name="firstName" onChange={handleFirstNameChange} />
```

Event names:
- should start with 'on'
- should not clash with builtin/native event names like 'onFocus' or 'onClick'
- should be CamelCase

```bash
// Bad (did not begin with 'on' )

handleFirstNameChange(){
firstNameChange(this.state.firstName);
}

render() {
  return (
<input name="firstName" onChange={handleFirstNameChange} />
  );
}
```

```bash
// Good

handleFirstNameChange(){
onFirstNameChange(this.state.firstName);
}

render() {
  return (
<input name="firstName" onChange={handleFirstNameChange} />
  );
}
```