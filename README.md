# broken-hashserve
### JumpCloud Broken-Hashserve QA Engineer Test

Manual test cases for the broke-hashserve application as part of the QA Engineer assignment for JumpCloud.  All Tests were performed manually on Max OSX 11.4

## Setup
Setup was perfored by following the recommended instructions but is outlined blow
1. Download/Clone the files per instruction via wget or download directly from the AWS URL
2. Add the following Environment variables to your .zrshc file 'export PORT=8088'

## User Stores/Acceptance Criteria
1. When launched, the application should wait for http connections.
2. It should answer on the PORT specified in the PORT environment variable.
 3. It should support three endpoints:
	 - A ​POST​ to ​/hash​ should accept a password. It should return a job identifier immediately. It should then wait 5 seconds and compute the password hash. The hashing algorithm should be SHA512.
	 - A ​GET​ to ​/hash​ should accept a job identifier. It should return the base64 encoded password hash for the corresponding POST request.
	 - A ​GET​ to ​/stats​ should accept no data. It should return a JSON data structure for the total hash requests since the server started and the average time of a hash request in milliseconds.
4. The software should be able to process multiple connections simultaneously.
5. The software should support a graceful shutdown request. Meaning, it should allow any
in-flight password hashing to complete, reject any new requests, respond with a 200 and
shutdown.
6. No additional password requests should be allowed when shutdown is pending.

## Difficualties/Limitations
Outlined in the test document, but the best usage for this this program would definitely be automation.  Due to the time consumption of many of the manual tests and difficulties, not all where performed.  Many tests are best run utilizing automation or a manual test case is simply not redundant enough to validate all scenarios

## Performing Tests
Launch application and follow Test Steps as outlined in the broken-hasherve_TESTCASES.rtf document https://github.com/jasonhilimire/broken-hashserve/blob/0c19f95360c0b2c10c8488bae8b13c7366eb8640/broken-hashserve_TESTCASES.rtf (due to formatting, its recommended to clone the repo and open the file manually)
