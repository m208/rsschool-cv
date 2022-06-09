# Andrey K
## Contacts 
* __Location:__ S-Petersburg, Russia
* [__GitHub: @m208__](https://github.com/m208)
* [__Discord: @m208#7830__](https://discordapp.com/users/160452172935462912)
* [__Telegram: @m20898__](https://t.me/m20898)

## About me
My name is Andrey. I have no any experience in the IT at all. 
I work as an engineer designer of industrial engineering systems. Ventilation, air conditioning, air purification systems, dust removal, vacuum systems, etc.
But programming has always been my hobby. I have done many different amateur projects. But none of them were commercial. I wrote scripts for automation, clickers, bots for online games, game cheats, various planners and online calculators, bots for Telegram and Discord. I have written a little in C++, C#, AutoHotkey, PHP, but mostly in JS.
Actually I started studying JS and programming itself fundamentally from the basics quite recently, and you won’t look at my code written 3-5 years ago without tears.
Now I plan to fill in the gaps, gain knowledge and skills on modern demanded technologies, and start a career in web development. I'm actually more interested in the back-end, but I think I should start with the front-end.

I want to tell in detail about a couple of interesting projects TL;DR

<details>
  <summary>(click to read) Farm bot for online MMORPG written from scratch ~ in 2017</summary>
  
My bots were farm for months, grinding tons of "valuable" resources to their owners. The average uptime (before some kind of error, or unforeseen situation) was about 36 hours. 

The bot continuously hunted the selected mobs (not harmless), collected loot from them, drop it to a personal location, controlled the condition of armor and weapon, ammunition supplies. In case of death, he returned from respawn, took the necessary equipment and everything was repeated. During the battle, the bot chose priority targets among the mobs, monitored and replenished its health, or, if the situation required it, retreated.

All information about the world around was drawn by the bot from the memory of the client's application process.
It took dozens or even hundreds of hours for reverse engineering with Cheat Engine. It was a very exciting and educational process. The most complex data structure known by me then was a matrix - an array of arrays. But surprisingly in the memory of the game, it was enough to find one unique parameter of a specific object, and everything else related to it lay somewhere nearby. It is only necessary to determine the size of this structures and set proper chains of pointers to this memory area. So, I first encountered objects and OOP from this side =)

The bot's actions were carried out by emulating mouse and keyboard clicks.
<details>
  <summary>Game with info overlay screenshot:</summary>
  
 ![Game screenshot](https://m208.github.io/rsschool-cv/img/fo.png)
</details>
Video on demand.

---
</details>

<details>
  <summary>(click to read) App: monitoring of Avito.ru new ads. 2020</summary>
  
Notifications in Telegram when a new ad appears on Avito for a given search query. Goal: catch interesting offers as quickly as possible. Today, such functionality is available in the Avito mobile app, but it was not there a year and a half ago.

Application structure:

Web scraping:
1. Information from Avito can be obtained by a regular GET request for link that user gave(the search query goes to Avito through url query parameters. Absolutely all search settings can be set in the link). A mobile user agent was used to minimize traffic. The content of the response was parsed as html, each ad has its own unique id, which is present in the layout. So, when the query was first launched, all ids were saved to the database, next then a comparison was made to search for new ones. Also, promo ads were cut off at the parsing stage.
2. Easy availability of data formed the basis of this project.
3. The only thing required was russian ip, a paid proxy server was used.

Frontend:
1. User log in to the frontend page using Telegram login widget.
2. User had his own settings for what hours not to send notifications (for example, at night).
3. User create tasks: search link, update interval (in minutes).
4. Tasks can be paused, resumed, deleted.

Backend:
1. NodeJS, Express.js for frontend.
2. Hosting app at openode.io.
3. Scrapper module in a cycle made requests to Avito for all running tasks at a given interval, if there were new ads, added info to the notifications queue.
4. Messenger module handled the notification queue for each user in the loop. If something needed to be sent and time allowed, a notification was sent to the user via Telegram.

Database:
1. Used MongoDB.
2. Each user had their own entry with id, settings, task list.
3. For each task, its own entry was created, where were stored ids of ads.
4. A queue for sending notifications was stored for each user. So in the morning the user receives a notification with all new ads, if any.

The app was actively used by several my friends, for about 6 months.

<details>
  <summary>App screenshots:</summary>
  
 ![App screen](https://m208.github.io/rsschool-cv/img/app.png)
 ![Telegram screen](https://m208.github.io/rsschool-cv/img/tg.png)
 ![App structure](https://m208.github.io/rsschool-cv/img/scheme.png)
</details>  

</details>


## Skills
* Git
* HTML, CSS, Figma
* PHP, JS, Node.JS
* JQuery, React, Express
* MongoDB, MySQL
* WordPress
* C++, C#, AutoHotkey
## Code example
```js
function getItems() {
    let i = 0;
    let table = '<table border = "1">';
    document.querySelectorAll('div.bi1').forEach(div => {
        i++;
        let title = div.querySelector('a.bj5').querySelector('span').innerText;
        let link = div.querySelector('a.bj5').href;
        let price = div.querySelector('span.ZI9r').innerText;
        let info = div.querySelector('span.a8b6').innerText;
        if (info.includes('Доставит')) info = '';
        table += `<tr>
                    <td>${i}</td>
                    <td><a href="${link}">${title}</a></td>
                    <td>${price}</td>
                    <td>${info}</td>
                </tr>`;
    })
    table += '</table>';
    copyToClipboard(table);
}
function copyToClipboard(data) {
    const blob = new Blob([data], { type: "text/html" });
    navigator.clipboard.write([new ClipboardItem({ [blob.type]: blob })])
        .then(() => { console.log('Copied'); })
        .catch(err => { console.log('Error: ', err); });
}
```
## Education
Saint Petersburg State University of Architecture and Civil Engineering (SPbGASU): HVAC engineer
## English
A2 Pre-Intermediate
