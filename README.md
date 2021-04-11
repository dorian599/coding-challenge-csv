# Coding Challenge

This is simple API with the following capabilities 
- Upload CSV file
- Parse the CSV and select only the data of a list of specific columns
- Insert the data into an in-memory DB ([mongodb-memory-server](https://www.npmjs.com/package/mongodb-memory-server)) Just for DEMO Purpose

**NOTE:** The full DEMO requirements could be found **[here](./REQUIREMENTS.md)**

## Technologies Used
- [ExpressJS](https://expressjs.com/) as API framework
- [Multer](https://www.npmjs.com/package/multer) for handle the multiplart upload
- [Lodash](https://lodash.com/) for fast picjup of the specific columns to work with
- [mongodb-memory-server](https://www.npmjs.com/package/mongodb-memory-server) to temporarily stop the CSV data
- [fast-csv](https://www.npmjs.com/package/fast-csv) for parse and formating CSV files
- [mongoosejs](https://mongoosejs.com/) as MongoDB object modeling
- [slug](https://www.npmjs.com/package/slug) for slugify the "provider name" that upload the CSV

## Mock Data
For this DEMO we have two(2) CSV files:
- [dev-challenge.csv](./mock/dev-challenge.csv) Contains mock data with the right columns
- [dev-challenge-extra-columns.csv](./mock/dev-challenge-extra-columns.csv) Contains mock data with the right columns and also with some extra columns to demostrate the well function of the api

**Note:** The mock data was generated using the tool [Mockaroo](https://www.mockaroo.com/). If you want to generate more CSV mock data, you can use the following already existing one schemas at Mockaroo:
- [dev-challenge](https://www.mockaroo.com/e7ee74d0)
- [dev-challenge-extra-columns](https://www.mockaroo.com/e7ee74d0)

## Spinup the DEMO

```
npm install
npm start
```

The API will be listening at `http://localhost:3000`

## Endpoints
- **POST** `/api/csv/upload` used to upload the CSV file
- **GET** `/api/cars` used to retrieve the already stored cars uploaded via the **/api/csv/upload** endpoint

## DEMO usage

**1-) Using PostMan collection**
You can use the following PostMan collection **[coding-challenge.postman_collection.json](./coding-challenge.postman_collection.json)** and select one of the mock CVS files to be summited.

**2-) Using cURL**
If you are more CLI guru, you also can use the following cURL commands to play with the DEMO API

`Upload CSV file`
```
curl --location --request POST 'http://localhost:3000/api/csv/upload' \
--form 'file=@"/path/to/file"' \
--form 'provider="Cars of the World"'
```

`GET cars`
```
curl --location --request GET 'http://localhost:3000/api/cars' \
--header 'Content-Type: application/json'
```

`NOTE:` remember to spinup the API first :D