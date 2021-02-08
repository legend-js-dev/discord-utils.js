# Discord-utils.js
## This package is an api wrapper for the [devs hub api](https://api.devs-hub.xyz) (made by me) & [cool-img-api](https://api.cool-img-api.ml) (made by my friend)
### Installing the package:
```
npm i discord-utils.js
```
### Getting started:
```js
const Discord = require("discord.js")
const { Client } = require("discord.js")
const util = require("discord-utils.js")
const client = new Client()

client.on("message", async (message) => {
if (message.content.startsWith("!communist")) {
let user = message.mentions.users.first()
let avatar = user.displayAvatarURL({ format: "png" })
let image = util.Canvas.communist(avatar)
message.channel.send({
files: [{
image
}]
})
}
})
```
