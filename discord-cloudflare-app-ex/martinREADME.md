https://discord.com/developers/docs/tutorials/hosting-on-cloudflare-workers
- created new app 'redditAwwwBot'
- copy applicationID and public key, go to 'bot' tabe and get token:
appId=b
publicKey=b
token=b

- click oauth2 tab, choose urlgenerator, click bot and application.commands scopes.
- check boxes for send messages and use slash commands
- copy url:
https://discord.com/oauth2/authorize?client_id=1247407872250347570&permissions=2147485696&scope=bot+applications.commands

- paste url into browser and follow auth flow to add bot to server

- - add cloudflare worker
- go to cloudflare dashboard / workers page
- create new service using same name as discord bot ("redditAwwBot")
- install wrangler cli (npm install wrangler --save-dev)
- run with `npx wrangler`

- go to cloudflare page for my service
- add env vars:
$ npx wrangler secret put DISCORD_TOKEN --name redditawwbot
    b
$ npx wrangler secret put DISCORD_PUBLIC_KEY --name redditawwbot
    b

$ npx wrangler secret put DISCORD_APPLICATION_ID --name redditawwbot
    b

- get guild id for discord channel from url like so:
https://discord.com/channels/a/b
guild id = a

set guild_id var as well:

$ npx wrangler secret put DISCORD_TEST_GUILD_ID --name redditawwbot
    b

- clone code from github project:
    https://github.com/discord/cloudflare-sample-app

- run npm i

- run this command before getting started to register commands:
$ DISCORD_TOKEN=a
DISCORD_APPLICATION_ID=b node src/register.js

- run code locally: npm start
- When a user types a slash command, Discord will send an HTTP request to a public endpoint. During local development this can be a little challenging, so we're going to use a tool called ngrok to create an HTTP tunnel.
- open new terminal window and run: npm run ngrok
- Copy the HTTPS link provided by the tool. It should look something like https://a.ngrok.io

- My link: "https://a.ngrok-free.app"
- open discord page for my bot, go to profile, set 'interactions (endpoint url)' to my link
- This is the process we'll use for local testing and development. When you've published your app to Cloudflare, you will want to update this field to use your Cloudflare Worker URL.

- when new changes are pushed to main branch, cloudflare worker auto gets updated.
- to manually push: run `npm run publish`

- error