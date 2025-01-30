hash13Backend\src> mkdir controllers db middlewares models routes utils 

npm install express dotenv cors helmet morgan
npm install --save-dev typescript @types/node @types/express ts-node nodemon


1) setup a pretter
make a ..prettierrc file in root dir

{

    "singleQuote": true,

    "bracketSpacing": true,

    "tabWidth": 2,

    "semi": true,

    "trailingComma": "es5"

}

make a .prettierignore in root dir 

*.env
.env
.env.example
/.vscode
/node_modules
./dist


======================================================

Connect a DataBase

sumitpal
e2xCBoAF3FZHm4Ds
mongodb+srv://sumitpal:e2xCBoAF3FZHm4Ds@cluster0.zfpfo.mongodb.net/

ther are two approact of connecting the code 


import dotenv from 'dotenv';

import express from 'express';

import cors from 'cors';

import mongoose from "mongoose";

import { DB_NAME } from './constants';

// Load environment variables

dotenv.config();

const PORT = process.env.PORT || 3000;

  
  
  
  

// Initialize Express

const app = express();

app.use(express.json());

app.use(cors());

  

;( async()=>{

    try {

       await mongoose.connect(`${process.env.MONGO_DB_URI}/${DB_NAME}`)

    //    express listionar

    // what if database is connected is successfully but for some resion ur express is not able to talk to database for this we are using listinersZ

        app.on("error",(error)=>{

            console.log("Err",error)

            throw error

        })

        // if

        app.listen(PORT, () => {

            console.log(`Server is running on port ${PORT}`);

          });

    } catch (error) {

        console.log("Error in conecting the DataBase")

        throw error

    }

})()

==================================================

  

const container = {

  hidden: { opacity: 0 },

  show: {

    opacity: 1,

    transition: {

      staggerChildren: 0.1,

    },

  },

}

