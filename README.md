# wws2zoom
A bot in zoom that uses a bot in IBM Watson Workspace (WWS) to replay a chat from WWS in a zoom chat with a zoom slash command 

`/wws @migrate <wwsSpaceID>`

## Disclaimer
Please be aware that I am not a professional developer and that this project is at a POC level of market readiness!

## Prerequisites
1) a zoom bot on https://marketplace.zoom.us **inside of the zoom account where you want to use it**, permitted to access the im.chat features and have a slash command /wws with an URL that matches your httpIn node for the wwsbot node (../zoom/wwsbot) (don't need to submit the app, skip the last step!)
2) a wws bot on https://developer.watsonwork.ibm.com/apps that is member of the space you want to migrate
3) a dropbox app on https://www.dropbox.com/developers/apps to store attachments and images from the wws stream
4) a node red installation that can access the internet
5) the watson workspace node collection from @stefanopog named node-red-contrib-wws
6) the dropbox nodes named node-red-node-dropbox
7) the simple message queue node from node-red-contrib-simple-message-queue for better controlling the flow of messages

I replaced the credentials in the code with dummy names like zoomClientSecret or zoomClientId, so have a look at it to replace it appropriately.

## Activating the bot for your account
You may have to install the new app by clicking "install" in the following URL:

`https://<myNodeRedHost>/zoom/install`

Then, execute the following oAuth from a zoom admin account of the account where you want to add and you should see:

`success`

Please consider that as of now zoom bots are not capable of multi-tenancy yet. You have to do all you do in ONE zoom account and the bot will work only there.

## Result
The bot gives help when he does not understand the message:
![My image](https://github.com/BerndGewehr/node-red-wws2zoom/blob/master/docs/error.jpg)

If the command is sent correctly, the bot will read the messages from WWS oldest-to-newest and post them into the given zoom chat where you sent the slash-command. Be sure that you added the wws app to the appropriate space in wws. Otherwise we are not allowed to read the wws content. The dropbox app/folder is needed because as of now, zoom bots can't post files and pictures to the stream. So we post dropbox public URLs instead and enjoy the unfurling inline preview from zoom.
