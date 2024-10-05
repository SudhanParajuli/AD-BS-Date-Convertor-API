Date Conversion API Documentation
=================================

Overview
--------

The Date Conversion API provides functionality to convert dates between the Bikram Sambat (BS) and Gregorian (AD) calendars. The API is built using Flask and supports Cross-Origin Resource Sharing (CORS).

Base URL
--------

`https://sudhang.pythonanywhere.com/`

API Endpoints
-------------

### 1\. Homepage

**Endpoint:** `/`

**Method:** `GET`

**Description:** Renders the documentation page for the API.

**Response:** Returns the `documentation.html` file.

`GET / HTTP/1.1`  
`Host: sudhang.pythonanywhere.com`

### 2\. Date Conversion Page

**Endpoint:** `/dateconvert`

**Method:** `GET`

**Description:** Renders the date conversion page for users.

**Response:** Returns the `dateconvert.html` file.

`GET /dateconvert HTTP/1.1`  
`Host: sudhang.pythonanywhere.com`

### 3\. Convert BS Date to AD Date

**Endpoint:** `/BStoAD/<int:year>/<int:month>/<int:day>`

**Method:** `GET`

**Path Parameters:**

*   `year` (int): The year in Bikram Sambat (BS).
*   `month` (int): The month in Bikram Sambat (BS).
*   `day` (int): The day in Bikram Sambat (BS).

**Description:** Converts a given BS date to its corresponding AD date.

**Response:** Returns a JSON object containing the AD date or an error message.

#### Response Format:

**Success:**

`{ "ad_date": { "day": <day>, "month": <month>, "year": <year> } }`

**Error:**

`{ "error": "Error message" }`

REQUEST
--------------
`GET https://sudhang.pythonanywhere.com/BStoAD/2080/1/1 HTTP/1.1`  
`Host: sudhang.pythonanywhere.com`

#### Successful Response:

`{ "ad_date": { "day": 14, "month": 4, "year": 2023 } }`

### 4\. Convert AD Date to BS Date

**Endpoint:** `/ADtoBS/<int:year>/<int:month>/<int:day>`

**Method:** `GET`

**Path Parameters:**

*   `year` (int): The year in Gregorian (AD).
*   `month` (int): The month in Gregorian (AD).
*   `day` (int): The day in Gregorian (AD).

**Description:** Converts a given AD date to its corresponding BS date.

**Response:** Returns a JSON object containing the BS date or an error message.

#### Response Format:

**Success:**

`{ "bs_date": { "day": <day>, "month": <month>, "year": <year> } }`

**Error:**

`{ "error": "Error message" }`

REQUEST
--------------
`GET https://sudhang.pythonanywhere.com/ADtoBS/2023/1/15 HTTP/1.1`  
`Host: sudhang.pythonanywhere.com`

#### Successful Response:

`{ "bs_date": { "day": 1, "month": 10, "year": 2079 } }`

Error Handling
--------------

If an error occurs during the conversion, the API will return a JSON object with an error message. Common errors may include:

*   Invalid date format or out-of-range dates.
*   Issues with the date conversion functions.

### Example Error Response:

`{ "error": "Invalid date format returned from conversion function." }`

Add Date Convertor In your website
----------------------------------

To embed the Date Conversion page in your own application, use the following iframe code:

`<iframe src="https://sudhang.pythonanywhere.com/dateconvert" width="100%" height="400px" style="border:none;"></iframe>`

Author
------

This API is developed by **Sudhan Parajuli**.

Notes
-----

Handle potential exceptions in client-side code to manage errors gracefully.
