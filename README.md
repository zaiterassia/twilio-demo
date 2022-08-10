# create a free account on twilio [here][twiliosignup]

# install twilio-cli

1. exécute powershell as administrator
2. run command `scoop bucket add twilio-scoop https://github.com/twilio/scoop-twilio-cli`
3. run command `scoop install twilio`
4. run command `twilio autocomplete`  

# login in console:

1. run command `twilio login` , enter accoount SID and Auth Token found in your twilio [console][twiconsole]
2. choose a shorthand for your profile
3. activate profile by running `twilio profiles:use <shorthand>` // replace shorthand by the profile name 

# config project

1. run command `cp .env.example .env`
2. define twilio env variables: accoount SID and Auth Token found in your twilio [console][twiconsole]
   apiKey, and apiSecret found in "C:\Users\<USER_NAME>\.twilio-cli\config.json"


# testing demo

1. create a conversation using command: `twilio api:conversations:v1:conversations:create --friendly-name "My First Conversation"`
	you will receive chat SID like "CHXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX " and a chat service SID like "ISXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"  
2. create a chat participant using command : `twilio api:conversations:v1:conversations:participants:create --conversation-sid CHXXXX --identity 	<USER_NAME>`
3. install token plugin: `twilio plugins:install @twilio-labs/plugin-token`
4. genearte a token for the participant: `twilio token:chat --identity <USER_NAME> --chat-service-sid ISXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`
5. relplace myToken in function getToken() in file `./src/ConversationsApp.js` 



[twiliosignup]: https://www.twilio.com/try-twilio
[twiconsole]: https://www.twilio.com/console