# Postman API Testing Master Class 🔥🚀

## 01. Introduction ✅

### Types of API

**There are two types of API's,**

1. Simple Object Access Protocol (SOAP)
2. Representational State Transfer (REST)

Both are the web services.

### API vs WebServices

- Web Service is an API wrapped in HTTP.
- All Web Services are API but APIs are not Web Services.
- A Web Service needs a network while an API doesn't need a network for its operation.

## 02. Environment Setup ✅

_Postman - API testing tool_

- We can do manual testing of API's using postman.
- Web / Desktop testing.
- Workspace: Area where we maintain files and saved.
- Create workspace, rename and delete.
- Creating Collection - contains number of folders and http requests.
  (Create, Rename, Delete and Run the collection)
- We can create any number of collections under workspace.

### HTTP Request

**REQUEST ➡️ APIs ➡️ RESPONSE**

**_GET_** ➡️ Retrieve the resource from database
**_POST_** ➡️ Create resource on database
**_PUT_** ➡️ Update existing resource on database
**_DELETE_** ➡️ Delete existing resource from database
**_PATCH_** ➡️ Update partial details of resource

![APIs Requests](API%20Requests.jpg)

### Validations

**status code**
**time**
**size data**
**response body(json/xml)**
**cookies**
**headers**

### HTTP Status Code

![Status Codes](Status%20Codes.jpg)

## 03. Creating Our Own APIs ✅

### Creating our own APIs

**Step1 - Install NodeJS**

**Step2 - Check Node and npm package manager version**

```bash
node -v
npm -v
```

**Step3 - Install json-server**

```bash
  npm install -g json-server
```

### Test / Validations

**JSON - JavaScript Object Notation**

**Key Value Pairs => key:value**

**_key is always included in "" quotation_**

### json-server

1. Open Terminal
2. Run the following command to run API testing

```bash
    json-server file_name
```

```json
{
  "firstname": "John",
  "secondname": null,
  "age": 30,
  "phone": 1234567890,
  "status": true
}
```

**Student Data**

```json
{
  "students": [
    {
      "sid": 101,
      "sname": "John",
      "grad": "A"
    },
    {
      "sid": 102,
      "sname": "Kim",
      "grad": "B"
    },
    {
      "sid": 103,
      "sname": "Scott",
      "grad": "C"
    }
  ]
}
```

### JSON vs XML

![JSON and XML](JSON%20and%20XML.jpg)

## 04. API Response Validations ✅

### Response Validations

**Status Code**
**Headers**
**Cookies**
**Response time**
**Response body**

### Assertion Validation

**pm - is a Library**
**_Functions/ Assertions are available for assertion validations._**
**_These Functions are written in JavaScript. Postman built-in uses JavaScript._**

`pm.function inside JavaScript Function`

**_We need to write our own JavaScript function and inside that we have to use `pm.function` for assertion validations._**

**Normal Function**

```javascript
pm.test (“Test Name”, function ()
				{
					// assertion;
				}
);
```

**Arrow Function**

```javascript
pm.test (“Test Name”, () =>
			 	{
					// assertion;
				}
);
```

### Testing Status Codes

1. Go to Postman
2. Create or Add a Request
3. In Request, go to `Tests` tab
4. Inside Test tab we have to write validation functions

**Test for the response status code:**

```javascript
pm.test (“Status code is 200”, () => {
pm.response.to.have.status(200);
});
```

**If you want to test for the status code being one of a set, include them all in an array and use one of:**

```javascript
pm.test (“Successful POST request”, () => {
pm.expect(pm.response.code).to.be.oneOf([201, 202]);
});
```

**Check the status code text:**

```javascript
pm.test (“Status code name has string”, () => {
pm.response.to.have.status(“Created”);
});
```
