# gs-to-array

Get an array from a public googlesheet

⚠️ The google sheet need to be public, the used url is the published google sheet like this one : `https://docs.google.com/spreadsheets/d/e/2PACX-1vQD4A1ad1rEqbJ0MGBv8UpKsT9EJalwdFJDMvbYOkAmjKIj6n0_SHoa_dgBKualCcxuqOD2g5AmI4Hp/pubhtml#`

⚠️ The header need to be on the first line of the google sheet

| id | name  | age |
| -- | ----- | --- |
| 1  | Bill  | 20  |
| 2  | Marie | 24  |

return

```
[
	{
		id: '1',
		name: 'Bill',
		age: '20'
	},
	{
		id: '2',
		name: 'Marie',
		age: '24'
	},

```

⚠️ Note that the written data are strings

## Install

```
npm install gs-to-array
```

## Use

Import and use the function `getArray()`, this function takes two parameters. The first parameter is the url of the public google sheet. The second parameter (optionnal) is the name of the sheet, if this parameter is not define the function

```
const gsta = require('gs-to-array');

const url = "https://docs.google.com/spreadsheets/d/e/2PACX-1vQD4A1ad1rEqbJ0MGBv8UpKsT9EJalwdFJDMvbYOkAmjKIj6n0_SHoa_dgBKualCcxuqOD2g5AmI4Hp/pubhtml#";
const sheetName = "page1";

//with an async/await function
(async () => {
    const array = await gsta.getArray(url, sheetName)
    console.log(array)
})()

// or with then/catch function
gsta.getArray(url, sheetName)
    .then(response=>console.log(response))
```
