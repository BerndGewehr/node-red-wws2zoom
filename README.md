# wws2zoom
A bot in zoom that uses a bot in IBM Watson Workspace (WWS) to replay a chat from WWS in a zoom chat with a zoom slash command 

```
/wws migrate <wwsSpaceID>
```

## Prerequisites:
1) a zoom bot on marketplace.zoom.us allowed to access the im.chat features (don't need to submit, skip the last step!)
2) a wws bot on https://developer.watsonwork.ibm.com/apps that is member of the space you want to migrate
3) a dropbox app on https://www.dropbox.com/home/Apps to store attachments and images from the wws stream
4) a node red installation that can access the internet
5) the watson workspace node collection from Stefano Pogliani named node-red-contrib-wws
6) the dropbox nodes named node-red-node-dropbox

I replaced the credentials in the code with dummy names like zoomClientSecret or zoomClientId, so have a look at it to replace it appropriately.
