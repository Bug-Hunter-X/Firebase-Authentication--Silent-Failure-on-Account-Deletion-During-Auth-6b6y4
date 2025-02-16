# Firebase Authentication: Silent Failure on Account Deletion During Auth

This repository demonstrates a bug in Firebase Authentication where an unexpected error occurs if a user's account is deleted or disabled during the authentication process. The error is not always easily caught, leading to silent failures.

## Bug Description
The Firebase Authentication SDK may not reliably handle situations where a user's account is deleted or disabled between the initiation and completion of the authentication process.  This can lead to unexpected behavior or silent failures in your application, making it challenging to debug. The standard error handling mechanisms might not always capture this specific scenario. 

## Reproduction Steps
1. Clone this repository.
2. Install the necessary packages: `npm install`
3. Run the `authBug.js` script. Observe the unexpected behavior or silent failure when the account is deleted or disabled during authentication. 
4. Run `authSolution.js` to see an improved approach.

## Solution
The solution involves adding robust error handling to specifically check for account deletion or disabling errors. This often involves checking for specific error codes or messages returned by the Firebase Authentication SDK.