# Steps
Install **node.js** [https://nodejs.org/en/download/](https://nodejs.org/en/) and make sure it went ok through:
```bash
$ node -v
$ npm -v
```
## Install VUE CLI through terminal
```bash
$ npm i -g @vue/cli @vue/cli-service-global
```
## Inside VSCode
VSCode terminal (ws is the folder where you want the project to be)
```c
$ vue create ws 
```
Then choose vue 2

``` bash
$ cd ws // folder we are working on
$ npm run serve // to run
```
### Bugs
When using the stopwatch if you hit "Reset" it will keep counting but from 0

### CSS
```c
font-family: Klavika Basic;
background-color: #009de0;
```

## Project setup
```bash
$ npm install
$ npm run serve
$ npm run build
```

## PG Packages
```bash
$ npm install sequelize pg pg-hstore --save
$ npm install sequelize-cli --save-dev
$ ./node_modules/.bin/sequelize init
```

Update config.json in the config folder
https://jes.al/2018/02/getting-started-with-express-vuejs-postgresql/

Then
```bash
$ ./node_modules/.bin/sequelize model:generate --name Visitor --attributes ip:string,user_agent:string
$ ./node_modules/.bin/sequelize db:create -> only if you dont already have a database
$ ./node_modules/.bin/sequelize db:migrate
```