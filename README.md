# Discord-utils.js
## This package is an api wrapper for the [devs hub api](https://api.devs-hub.xyz) (made by me) & [cool-img-api](https://api.cool-img-api.ml) (made by my friend)
### Installing the package:
```
npm i discord-utils.js
```
### Getting started:
```js
const Discord = require("discord.js") //require discord
const { Client } = require("discord.js") //require client
const util = require("discord-utils.js") //require discord-utils.js
const client = new Client() //create the client

client.on("message", async (message) => {
if (message.content.startsWith("!communist")) {
let user = message.mentions.users.first()
let avatar = user.displayAvatarURL({ format: "png" }) //gets the url of the members avatar
let image = util.Canvas.communist(avatar) //creates the communist image
message.channel.send({
files: [{
image
}]
}) //send the image
}
})

client.login("token")
```
