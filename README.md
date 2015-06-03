# APITests
This repository contains the [Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en) tests we use for automated testing of the API. We'll soon be sharing the DB we run these tests against as well. These tests form the bulk of the testing done against the API server, so they will reflect what we test and expect to work. Our goal is for the community to help us improve our testing, and therefore the API quality, continually by submitting pull requests containing additinal test cases. There are two main folders in this repository
- **Postman collections:** This folder contains an export of the postman tests that can be imported into the postman tool. Some of these tests may require data files that provide input data for the tests.
- **Postman Data Files:** This folder contains data files that are inputs for many of the tests in the Postman collections.

When submitting a pull request for a test case, please be sure to try to follow the existing format and conventions used in other tests. Failure to do so will result in delays due to the effort to rework the test, or a rejection of the test altogether.

The tests also serve as a great repository of samples illustrating how to use the API, so this is a great place to check if you're wondering:
- How do I create an API request to do a certain task?
- Has NCR tested a certain scenario of usage for a given API request?
- How can I share a problem I've found with the API in a way that makes it easy for NCR to see and reproduce the issue?
- How can I improve the testing NCR does to ensure a key usage scenario is always tested going forward?

## Running Postman Tests
These tests are intended to be run using the "Test runner" feature of Postman, and can be run manually (with the [Jetpacks](https://www.getpostman.com/docs/jetpacks_intro) add on), or automated via the [Newman](https://www.getpostman.com/docs/newman_intro) command line collection runner for Postman.

### Setting up environments
The tests use the [Environments](https://www.getpostman.com/docs/environments) feature of Postman to allow the same test to be easily modified to run in different test environments. In order to use these tests, you must setup an environment with the following values:
 - Authorization
  - This will contiain the basic authorization header *value*. Should be `basic <your base64 encoded credentials here>`
 - APIKey
  - This is the APIKey used to run the tests. It doesn't matter what key, as long as it's valid on the server you are testing against.
 - Protocol
  - Should be `https://` for SSL protected servers
 - Server
  - The name of your server as it should appear in the URI/web address
 - Port
  - The port your server is running on
 - Content-Type
  - Should be `application/json`
   
### Executing a test
The following steps can be used to manually execute a test in Postman, assuming the JetPacks addon is installed:
- Sync this repository to the machine from which the tests will be run, so you have a local copy of all test files.
- Launch Postman.
- Ensure you have a proper environment setup as described above.
- Click the "Import" button at the top of the Postman application.
- Select "Choose Files" and navigate to the local copy of the `Postman Collections` folder that was synced from this repository.
- Select a `*.json.postman_collection` file containing a test collection. The collection will show up on the "Collections" tab on the left hand panel in Postman.
- Click the "Runner" button to launch the test runner.
- Select the test collection to run, as well as the environment.
- If the test collection requires a data file for input, click "choose file" and navigate to the `Postman Data Files` folder to select the proper test file (NOTE: We need to add documentation or a naming convention to make this more evident/obvious)
- Click "Start Test Run" to execute the tests
 
