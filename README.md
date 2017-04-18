# LineBot-Dotnet

# Installation 
### 1. Nuget: LineBotSDK
### 2. Server: Azure web application

# API
Create LineBot instance with specified configuration.
```js
string ChannelAccessToken = "your access token";
string UserId = "your user id";
isRock.LineBot.Bot bot;
//create bot instance
bot = new isRock.LineBot.Bot(ChannelAccessToken);
```
## Get the receieve message from line
```js
//取得 http Post RawData(should be JSON)
string postData = Request.Content.ReadAsStringAsync().Result;
//剖析JSON
var ReceivedMessage = isRock.LineBot.Utility.Parsing(postData);
var UserSays = ReceivedMessage.events[0].message.text;
```
## reply token
```js
var ReplyToken = ReceivedMessage.events[0].replyToken;
```
## chat type
get the chat type like id/room id/group id 
```js
var type = ReceivedMessage.events[0].source.type;
```
## reply message
```js
bot.ReplyMessage(string ReplyToken, string Message)
```
## push message
```js
bot.PushMessage(string ToUserID, ButtonTemplate message)
```
# Inspired By
-[.Net Walker](http://studyhost.blogspot.tw/2016/12/)

# Demo
![]image(https://goo.gl/0Loaaz)


