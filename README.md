# wws2zoom
A bot in zoom that uses a bot in IBM Watson Workspace (WWS) to replay a chat from WWS in a zoom chat with a zoom slash command 

```
/wws migrate <wwsSpaceID>
```

## Prerequisites:
1) a zoom bot on marketplace.zoom.us allowed to access the im.chat features
2) a wws bot on https://developer.watsonwork.ibm.com/apps that is member of the space you want to migrate
3) a node red installation that can ccess the internet
4) the watson workspace node collection from Stefano Pogliani named node-red-contrib-wws
5) a dropbox app on https://www.dropbox.com/home/Apps to store attachments and images from the wws stream
