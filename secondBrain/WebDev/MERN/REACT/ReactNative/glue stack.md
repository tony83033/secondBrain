
https://gluestack.io/ -> something like shadcn for React Native

npx expo install react-native-appwrite react-native-url-polyfill



import { Client, Account, ID } from 'react-native-appwrite';

const client = new Client()
    .setProject('6780e3ff00052183da93')
    .setPlatform('com.dude');
