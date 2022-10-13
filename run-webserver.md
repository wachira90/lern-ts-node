# Node.js, TypeScript, and Express to Build a Web Server


## npm init -y

File: package.json

````

 {
  "name": "typescript-nodejs",
  "version": "1.0.0",
  "description": "This is a test web server.",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
````

## install package

````
npm install express

npm install typescript ts-node @types/node @types/express --save-dev

````

#### OR

````
yarn add -s express

yarn add -s typescript ts-node @types/node @types/express

````

## How to Create your tsconfig.json

npx tsc --init

File: tsconfig.json

````

 {
    "compilerOptions":{
        /*Language and Environment*/
        "target":"es5",

        /* Modules */
        "module":"commonjs",
        //"rootDirs": [],

        /* Interop Constraints */
        "esModuleInterop": true,
        "forceConsistentCasingInFileNames": true,

        /* Type Checking */
        "strict": true,

        /* Completeness */
        "skipLibCheck": true

        /* Emit */
        //"outFile": "./",
        //"outDir": "./",
    }
}
````

## Create a TypeScript, Node.js and Express Web Server

File: index.ts

````
import express from 'express';

const app = express();

app.get('/', (req, res) => {
    res.send('This is a test web page!');
})

app.listen(3000, () => {
    console.log('The application is listening on port 3000!');
})

````

## Run your code to create the webserver

````
npx ts-node index.ts
````

### more info 


https://www.staging-typescript.org/tsconfig


