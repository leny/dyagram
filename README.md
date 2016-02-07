# dyagram

> Micro validation schema for javascript structures

* * *

**dyagram** is a simple validation schema for javascript objects, made to be easy to learn and use.

## dyagram schema

A **dyagram** schema is a simple `json object`, representing the structure to validate.

### Check the presence/absence of a property

Give a `boolean` value to a property in schema to check for its presence (or absence) in structure, regardless of its type nor value.

#### Example

```javascript
{
    "lastname": true, // will check for the presence of the lastname property
    "age": false // will check for the absence of the age property
}
```

### Check the type of a property

Give a `string` value to a property in schema to check its type, regardless of its value.

#### Supported type

The following types are supported: `boolean`, `string`, `number`, `array`, `object`.

#### Example

```javascript
{
    "lastname": "string",
    "firstname": "string",
    "age": "number",
    "address": "object",
    "skills": "array"
}
```

### Nested object

**dyagram** schema support nesting.

#### Example

```javascript
{
    "lastname": "string",
    "firstname": "string",
    "age": "number",
    "address": {
        "street": "string",
        "number": "number",
        "city": "string",
        "location": {
            "latitude": "number",
            "longitude": "number"
        }
    }
}
```

### Check for value

You can have more control on a property by using an `array`: the _first_ value of the array define the type of the property, the following values are defined by the following rules.

#### `boolean`

The second value defines the value of the property.

##### Example

```javascript
{
    "is_happy": [ "boolean", true ] // will check for the property is_happy to be a boolean with the "true" value
}
```

#### `string`

If the second value is a `string`, it defines the value of the property ; if its a RegExp, it defines a pattern that the property must pass.

##### Example

```javascript
{
    "name": [ "string", "leny" ], // will check for the property name to be a string with the "leny" value
    "zip_code": [ "string", /[a-zA-Z0-9]*/ ] // will check for the property zip_code to be a string with a value passing the given regexp
}
```

_TO BE CONTINUED_
