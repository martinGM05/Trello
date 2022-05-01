# Trello

This project only has the conection to Trello from Node.

## App.js
```javascript
require('dotenv').config()

if(!process.env.TOKEN && !process.env.KEY){
  throw new Error('No hay configuración con Api Key y con Token')
}

let Trello = require("trello");
let trello = new Trello(process.env.KEY, process.env.TOKEN);

let cardTitle = `Card Nueva ${new Date()}`

trello.addCard(cardTitle, "LaunchX Card Description", "626ebd4fc53dba77cf28c124",
	function (error, trelloCard) {
		if (error) {
			console.log('Could not add card:', error);
		}
		else {
			console.log('Added card:', trelloCard);
		}
	});
```

##   Demo
![Trello](https://user-images.githubusercontent.com/63875704/166159508-30844a1c-c591-4697-9158-0247c0886bb9.gif)



For more information check this [Repo](https://github.com/norberteder/trello).
