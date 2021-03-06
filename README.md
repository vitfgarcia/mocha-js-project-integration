# Project for REST API testing with BDD

This is a base project for **integration** tests for REST APIs using node.js
The objective of this project is to provide a structured code that meets the need of a Quality Assurance Team on a daily basis.

## Structure

- **test-results/reports** : folder that will contain all the tests results in an html file. The name pattern is **test${date_time}**. **Note: The report will only be generated when the -R flag is passed**

- **test** : folder that contains all the strucure of the project.

- **test/commons**: contains all files and functions that will be shared in all tests. Ex:API base URL

- **test/config**: framework config files. Ex: mocha and mocha-prepare configuration.

- **test/helpers**: specific libraries that contain the abstraction of proccesses that the test does not need to execute like a request.

- **test/suite**: contain the actual tests

- **test/suite/{route}**: contains the necessary data to execute tests (dataset.js), the route tests({route}.test.js) and support functions ({route}.js)

## Test Notes

- All test files must be inside the suite folder and the file must be named **{route}.tests.ts**

## Running Tests

Execute the following command or configure a new one on **package.json** scripts.

```
yarn run tests
```

- Flags to be passed:
  - '--file fileName' or '-F fileName' where fileName is the name of the test file to run.
  - '--path folderPath' or '-P folderPath' where folderName is the name of the folder where the test files are (suite is the default value).
  - '--test testPattern' or '-T testPattern' where testPattern is the 'name or pattern' of the test you wanna run.
  - '--report' or '-R' will generate a report in HTML format using mochawesome reporter
  - '--env environment' or '-E environment' to pass the env you wanna run the tests. (This will use dotenv to load environment variables placed inside the folder test/config/environments, where the file loaded is ${environmentName}.env)

### Note that if you pass -F or --file it will be necessary to pass the -P or --path to indicate the folder that the file is present

## Mocha and Chai

- For information on the Mocha (Hooks and other information) access https://mochajs.org/

- For reference on how to assert look at http://www.chaijs.com/api/bdd/
