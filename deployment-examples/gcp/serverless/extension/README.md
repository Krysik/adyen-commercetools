## Deploy as GCP Cloud Function

1. Run 'npm run zip-serverless'. It helps to execute following steps
   - Rename index.googleFunction.js to index.js
   - For deployment to GCP Cloud Function, bundle the following files and folders into a .zip file and upload it in GCP console.
      - src
      - resources
      - index.js
      - package.json
      
2. Specify the `extensionTrigger` as the entry point function in your GCP Cloud Function configuration.
3. When the extension module is running as GCP Cloud Function **it will NOT create** the required resources like custom 
types or commercetools API extension for you. Please follow the [manual resource creation guide](../../../../extension/docs/HowToRun.md#creating-required-resources-manually) instead. 
4. By default, the deployed cloud function is not allowed to be called without permission. It returns 403 http status when it is called. Please add desired user groups into 'Cloud Functions Invoker'. 