# GoApptiv REST API Standards

- [Methods](#methods)
- [Naming Conventions](#naming-conventions)
- [HTTP Statuses](#http-statuses)

<a name="methods"></a>

## Methods

Use the following methods for different data operations

- **GET** - Retrieve existing data

- **POST** - Add new data

- **PUT** - Update existing data

- **PATCH** - Update a subset of existing data

- **DELETE** - Delete already existing data

**Example:**

`GET`: /appointments - To get the list of appointments

`POST`: /appointments - To create a new appointment

`PUT`: /appointments/{id} - To update the appointment by id

`DELETE`: /appointments/{id} - To delete the appointment by id

<a name="naming-conventions"></a>

## Naming Conventions

### Use Nouns

Use Nouns in URIs, RESTful URIs should not indicate any kind of CRUD (Create, Read, Update, Delete) functionality in the URIs. Make use of the HTTP methods mentioned above to indicate the functionality.

**Example:**

`GET`: /appointments/{id} instead of /getAppointment

### Pluralize the URIs

Pluralize the URIs if you are returning a list and singular if it a single resource

**Example:**

`GET`: /orders instead of /order

`GET`: /users/{id}/address instead of /users/{id}/addresses

### Query parameters

To apply some sort or filter to the data use query params in the URI.

**Example:**

`GET`: /appointments?status=active instead of /getActiveAppointments

### Lowercase and Dashes

Use Lowercase in the URIs and dashes to join multiple words in the URI.

**Example:**

`GET`: /card-number instead of /cardNumber

### Use Standard Variable naming convention for request and response

Use a standard variable naming convention in both request and response.

**Example:**

`REQUEST`: card_number: 12345678

`RESPONSE`: card_number: 12345678

Instead

`REQUEST`: cardNumber: 12345678

`RESPONSE`: card_number: 12345678

<a name="http-statuses"></a>

## HTTP Statuses

Use Standard HTTP statuses for all response,

<table>
  <tr>
    <td>Status Code</td>
    <td>Message</td>
    <td>Example</td>
  </tr>
  <tr>
    <td>200</td>
    <td>Success</td>
    <td>When the object is created and returned</td>
  </tr>
  <tr>
    <td>201</td>
    <td>Created</td>
    <td>When the object is created</td>
  </tr>
  <tr>
    <td>400</td>
    <td>Bad Request</td>
    <td>When the server doesn’t understand the request or some validation error</td>
  </tr>
  <tr>
    <td>401</td>
    <td>Unauthorized</td>
    <td>When the user is not authorized for the action</td>
  </tr>
  <tr>
    <td>404</td>
    <td>Not Found</td>
    <td>When the api is not present</td>
  </tr>
  <tr>
    <td>429</td>
    <td>Too many requests</td>
    <td>When we have applied throttle to control the requests</td>
  </tr>
</table>
