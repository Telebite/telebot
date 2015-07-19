# Telebot

A Telegram Bot for Telebite conv.

Thanks to: [node-telegram-bot](https://github.com/crisbal/Node-Telegram-Bot)
Thanks to: [node-telegram-bot-api](https://github.com/yagop/node-telegram-bot-api) 

TODO TO BE MODIFIED
## How to use the bot

* Clone/Download/Fork the repository
* ```npm install```
* Create a Bot Account 
    * Get the associated token (https://core.telegram.org/bots/#botfather)
* Edit config.js
    * Set ```telegramToken``` with the auth token of your bot
    * Edit ```activePlugins``` if you want to edit the active plugins. It is an array of the filenames of the active plugins. 
* Run the bot
    * ```node bot.js``` 
    * Stop it at any time with CTRL+C

## Plugins

Plugins can be easly written with a basic understanding of Javascript.

Check the ```plugins``` folder to see the available plugins and check each file to see a basic explanation.

### Writing custom plugins

* Take a look at the provided plugins in the ```plugins``` folder
* Create a ```.js``` file in the ```plugins``` folder

Basic Skeleton
``` javascript
var pluginName = function(){

    this.init = function(){
        //this will be executed when the bot starts
    };

    this.doStop = function(){
        //this will be executed when the bot shuts down
    };  


    this.doMessage = function (msg, reply) {
        //this will be executed whenever your bot get a message

        /*
            1. Check if the msg.text matches the trigger for your plugin
            2. Do stuff you need
            3. Produce reply 
                replyText = {type:"text", text:"Message you want to post"}
                replyAudio = {type:"audio", audio:"path/to/audio.mp3"}
            4. Post the reply
                reply(replyText); //for example

        */
    };

};

module.exports = pluginName;
```
## TODO
* Better way to handle plugins (?), I need suggestion on this
* Common utilities module (downloading file, downloading web page, ...)
* Improve the code
* More plugins
* TTS
    * Fix random exceptions that sometimes happens
* SET
    * Check if the database file exists before saving/loading

## Contributing

Did you made a plugin you want to share with everyone? 

Submit a pull request! 

This project will only grow if *YOU* help!
