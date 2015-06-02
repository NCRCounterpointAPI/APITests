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

