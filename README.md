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
let image = await util.Canvas.communist(avatar)
message.channel.send({
files: [{
name: "image.png",
attachment: image
}]
})
}
})

client.login("token")
```
### if you use a command handler it would look like this:
```js
const { Canvas } = require("discord-utils.js")

module.exports = {
name: "communist",
description: "sends an image with the communist filter",
run: async (client, message, args) => {
let user = message.mentions.users.first() || message.author
let avatar = user.displayAvatarURL()
let image = await Canvas.communist(avatar)
message.channel.send({
files: [{
name: "image.png",
attachment: image
}]
})
}
}
```
### for random cats, dogs, or birds:
```js
const { random } = require("discord-utils.js")

module.exports = {
name: "dog",
description: "sends a random dog picture",
run: async (client, message, args) => {
let image = await random.dog()
message.channel.send({
files: [{
name: "image.png",
attachment: image
}]
})
}
}
```

### for using the util stuff:
```js
const { Utils } = require("discord-utils.js")

module.exports = {
name: "emojify",
description: "emojifies provided text",
run: async (client, message, args) => {
let text = args.join(" ")
if (!text) return message.channel.send("Provide text to emojify!")
try {
let emojify = await Utils.emojify(text)
return message.channel.send(emojify)
} catch (error) {
console.log(error)
} //if you get errors join the support server on discord
}
}
```
### using the djsDocs method on Utils:
```js
const { Utils } = require("discord-utils.js")

module.exports = {
name: "docs",
aliases: ["djs"],
description: "searches the djs docs for the provided query",
run: async (client, message, args) => {
let text = args.join(" ")
if (!text) return message.channel.send("Provide the query!")
try {
let embed = await Utils.djsDocs(text)
return message.channel.send({
embed: embed
})
} catch (error) {
console.log(error)
} //if you get errors join the support server on discord
}
}
```

### Links:
- Discord Server - [click here](https://discord.gg/BPCs7qXXbk)
- Documentation - [click here](https://l3g3nd-0001.gitbook.io/discord-utils-js/)
- Surprise - [click here](https://youtu.be/dQw4w9WgXcQ)

#### Note: the list of Canvas methods are listed on the documentation
