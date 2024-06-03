- Create bot
- Click 'bot' left side page
- Copy token: abc123
- Click oauth2 in sidebar
- Under oauth2 url generator change scopes:
- Add 'bot' scope, 'applications.commands',  and under bot permissions: 'send messages'
- After scopes are added, copy url at bottom of page:
https://discord.com/oauth2/authorize?client_id=1243385408281251975&permissions=3072&scope=bot
- Copy url and paste it into browser, install bot
- Start with code from this repo:
https://github.com/discord/discord-example-app.git
- cd discord-example-app
- npm i
- fill out discord-example-app/.env

- install slash commands: npm run register
- run the app: node app.js
- install ngrok
- add ngrok token: https://dashboard.ngrok.com/get-started/setup/macos
- setup interactivity by running: ngrok http 3000
- copy forwarding address that starts with 'https' 
- ex:https://1234-someurl.ngrok.io
- https://96a5-24-19-122-236.ngrok-free.app

- go to app settings
- general info tab, interactions endpoint url, paste url there and append /interactions to it
- https://96a5-24-19-122-236.ngrok-free.app/interactions

- - Bot setup & testing:
- Clone this repo, run npm i, setup ngrok.
- Run ngrok and node app.js both together
- In discord channel where i installed app, run `/test`

- Followed dev quick start guide:
https://discord.com/developers/docs/quick-start/getting-started

- Next steps:
- browser the examples/ folder
- explore discord devs platform: https://discord.com/developers/docs/intro
- do this tutorual (host discord bot on cloudflare worker): https://discord.com/developers/docs/tutorials/hosting-on-cloudflare-workers
- discord developer platform https://discord.com/developers/docs/topics/community-resources
- join discord developers discord: https://discord.com/invite/discord-developers
