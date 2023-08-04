<!-- <template>
    <div>
      <h1>Login Page</h1>
      <button @click="loginWithGoogle">Login with Google</button>
    </div>
  </template>
  
  <script>
  import * as AWS from 'aws-sdk';
  import AmazonCognitoIdentity from 'amazon-cognito-identity-js';
  
  export default {
    name:"LoginView",
    methods: {
      loginWithGoogle() {
        try {
    // Initialize the Amazon Cognito credentials provider
    AWS.config.region = 'ap-northeast-1';
        AWS.config.credentials = new AWS.CognitoIdentityCredentials({
          IdentityPoolId: 'ap-northeast-1:60fbbcfa-1a6f-4aed-ba1f-614dce3f07e3',
        });
  
        // Create the CognitoUserPool object
        const poolData = {
          UserPoolId: 'ap-northeast-1_2wJQ2Fja0',
          ClientId: '6imjmm036nks30abhkn04jldnv'
        };
        const userPool = new AmazonCognitoIdentity.CognitoUserPool(poolData);
  console.log(userPool)
        // Create the Google login URL
        const authData = {
          RedirectUri: 'https://dkkdkbbcdj9bw.cloudfront.net/index.html',
          TokenScopesArray: ['email', 'profile'],
          UserPoolId: 'ap-northeast-1_2wJQ2Fja0',
          AppClientId: '6imjmm036nks30abhkn04jldnv'
        };
        const auth = new AmazonCognitoIdentity.CognitoAuth(authData);
  
        // Initiate the Google login process
        auth.getSession();
  } catch (error) {
    console.error("An error occurred:", error);
  }
       
      }
    }
  };
  </script>
   -->
   <template>
    <div>
      <amplify-authenticator>
        <amplify-sign-in federated="google"></amplify-sign-in>
      </amplify-authenticator>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LoginView',
  };
  </script>
  
  