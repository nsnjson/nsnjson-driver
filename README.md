# NSNJSON Driver

## NSNJSON - Not So Normal JSON

![nsnjson_logo](https://raw.githubusercontent.com/wiki/nsnjson/nsnjson-driver/images/nsnjson_logo.png)

## Why?

Have you ever think about JSON with only 4 types: **number**, **string**, **array**, **object**? :)

What if your programming language or some another ecosystem doesn't support **null** or **true**/**false** as a types or a special values?

If it is your case then NSNJSON comes to help you! :)

The NSNJSON operates only 4 types - **number**, **string**, **array**, **object**!

Also, it defines types mapping table:

| JSON type    | null   | number | string | true   | false  | array  | object |
|:-------------|:------:|:------:|:------:|:------:|:------:|:------:|:------:|
| NSNJSON type | 0      | 1      | 2      | 3      | 3      | 4      | 5      |


## How?

For every JSON type NSNJSON defines special presentation which is absolutely valid JSON.

NSNJSON presentation is always JSON object.

Such object always contains field **"t"** (which means **type** of source JSON type).

Also, for all JSON types except **null** the object always contains field **"v"** (which means **value** of source JSON type).

JSON object field has a name. So, NSNJSON saves this information in field **"n"** (which means **name** of field JSON object).

## Examples?
**null**
```javascript
// json
null

// nsnjson
{ "t": 0 }
```
**number**
```javascript
// json
1007

// nsnjson
{ "t": 1, "v": 1007 }
```
**string**
```javascript
// json
"Hello"

// nsnjson
{ "t": 2, "v": "Hello" }
```
**boolean** / **true**
```javascript
// json
true

// nsnjson
{ "t": 3, "v": 1 }
```
**boolean** / **false**
```javascript
// json
true

// nsnjson
{ "t": 3, "v": 0 }
```
**array**
```javascript
// json
[null, true, false]

// nsnjson
{
  "t": 4,
  "v": [
    {
      "t": 0
    },
    {
      "t": 3,
      "v": 1
    },
    {
      "t": 3,
      "v": 0
    }
  ]
}
```
**object**
```javascript
// json
{
  "null_field": null,
  "true_field": true,
  "false_field": false
}

// nsnjson
{
  "t": 5,
  "v": [
    {
      "n": "null_field",
      "t": 0
    },
    {
      "n": "true_field",
      "t": 3,
      "v": 1
    },
    {
      "n": "false_field",
      "t": 3,
      "v": 0
    }
  ]
}
```

## Drivers?

Yeah! Available drivers:
- [NSNJSON Node.js Driver](https://github.com/nsnjson/nsnjson-nodejs-driver)
- [NSNJSON Java Driver](https://github.com/nsnjson/nsnjson-java-driver)

## Any contacts?

Yeah! Please, feel free to contact me by email: jxcoder@ya.ru (Maks Atygaev)
