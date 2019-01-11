# wws2zoom
A bot in zoom that uses a bot in IBM Watson Workspace (WWS) to replay a chat from WWS in a zoom chat with a zoom slash command 

`/wws migrate <wwsSpaceID>`

## Prerequisites:
1) a zoom bot on https://marketplace.zoom.us **inside of the zoom account where you want to use it**, permitted to access the im.chat features and have a slash command /wws with an URL that matches your httpIn node for the wwsbot node (../zoom/wwsbot) (don't need to submit the app, skip the last step!)
2) a wws bot on https://developer.watsonwork.ibm.com/apps that is member of the space you want to migrate
3) a dropbox app on https://www.dropbox.com/developers/apps to store attachments and images from the wws stream
4) a node red installation that can access the internet
5) the watson workspace node collection from Stefano Pogliani named node-red-contrib-wws
6) the dropbox nodes named node-red-node-dropbox
7) the simple message queue node from node-red-contrib-simple-message-queue for better controlling the flow of messages

I replaced the credentials in the code with dummy names like zoomClientSecret or zoomClientId, so have a look at it to replace it appropriately.

You my have to install the new app by clicking "install" in the follwoing URL:

`https://<myNodeRedHost>/zoom/install`

Then, execute the following oAuth from a zoom admin account of the account where you want to add and you should see:

`success`

The bot gives help when he does not understand the message:
![My image](https://github.com/BerndGewehr/wws2zoom/blob/master/docs/error.jpg)
