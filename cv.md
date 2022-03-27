# Andrey K
## Contacts 
* __Location:__ S-Petersburg, Russia
* __GitHub:__ [m208](https://github.com/m208)
* __Discord:__ [m208#7830](https://discordapp.com/users/160452172935462912)
## About me
In search of new knowledge
## Skills
* HTML, CSS
* PHP, JS, Node.JS
* JQuery, React, Express
* MongoDB, MySQL
* WordPress
* C++, C#, AutoHotkey
## Code example
```
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
## Experience
I only had a lot of personal hobby projects
## Education
I am self-taught
## English
A2 Pre-Intermediate