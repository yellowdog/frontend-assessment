## Application Requirements

This application was built to support frontend engineers developing recruitment assessments with the following requirements:

A simple API that allows a user to manage contact information.

A user must be able to:
* Create new contacts
* Update a specified contact
* Delete a specified contact
* See all of their existing contacts
* See a specific contact

A contact has the following information:
* A first and last name
* Optionally, a home address
* Optionally, a work address

An address has the following information:
* A type (work or home)
* Optionally, a house number
* A street address, city and postcode.

All requests should take no longer than 200ms.

## Run

```
docker-compose up -d
```

## API

All endpoints are exposed under `http://localhost:8080/api/contacts`

### Find all contacts

```http request
GET http://localhost:8080/api/contacts
```

### Create contact

```http request
POST http://localhost:8080/api/contacts
Content-Type: application/json

{
  "firstName": "John",
  "surname": "Smith",
  "addresses": [
    {
      "addressType": "HOME",
      "houseNumber": "214",
      "streetAddress": "Example Road",
      "city": "Example City",
      "postCode": "BS24 3SQ"
    }
  ]
}
```

### Get contact

```http request
GET http://localhost:8080/api/contacts/{{contacts_id}}
```

### Update contact

```http request
PUT http://localhost:8080/api/contacts/{{contacts_id}}
Content-Type: application/json

{
  "id": "{{contacts_id}}",
  "firstName": "John",
  "surname": "Doe",
  "addresses": [
    {
      "addressType": "HOME",
      "houseNumber": "214",
      "streetAddress": "Example Road",
      "city": "Example City",
      "postCode": "BS24 3SQ"
    }
  ]
}
```

### Delete Contact

```http request
DELETE http://localhost:8080/api/contacts/{{contacts_id}}
```

## Database

Mongo is exposed at `http://localhost:27017`
