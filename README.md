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

### PostGreSQL Packages to install
```bash
npm install --save pg
npm install --save dns pg-native
```

OR

```bash
$ npm install sequelize pg pg-hstore --save
$ npm install sequelize-cli --save-dev
$ ./node_modules/.bin/sequelize init

```


## Project setup
```
$ npm install
$ npm run serve
$ npm run build
```