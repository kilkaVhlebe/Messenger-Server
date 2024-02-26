# Messenger Web Server
## Description
This my learning project for messenger i made whith my partner.
It used websokets technology under standart express.
## Installation and developing
Clone repository
```
git clone https://github.com/tugaserya/Messenger-API.git
cd Messenger-Server
```
install dependencies
```
npm i
```

Create your [firebase](https://firebase.google.com/]) project and download serviceAccountKey.json in his setthings.
Then add it in main project directory. This thing need for notification in messenger.
## Running
This server use pm2 for logs, monitoring and stable work.
Run:
```
npm start
```
For development run:
```
npm run dev
```

## API

### HTTPS

#### Users
``/registration`` - Creating user account


``/login`` - User authorization

``/search`` - Searching user in Database for chat creating

``/logout`` - Unauthorize user

#### Messages
``/get_past_messages`` - Load 300(based on offset) messages in chat

#### Files
``/avatar_upload`` - Downloading templated base64 string from client(It's converting to image on client side).

``/avatar_download`` - Send templated base64 string to client.

``/avatar_delete`` - remove avatar info from Database. Set default value(0).

``/file_upload`` - Part of file sending logic. Download file from user.

``/file_download`` - Part of file sending logic. Send file to user.

#### Chats
``/chat_creating`` - Creat chat between 2 users.


### WebSocket's
I made custom routing based on switch-case. I know about socket.io. I wanted to do it myself for better understanding of tech.

#### Messages
``new_message`` - Handle new message from sender to recipient. Call Firebase notification if recipient isn't online

``update_message`` - Handle function "edit message" on client.

``archive_message`` - Handle function "delete message" on client.

``is_readed_message`` - Handle the status of a message indicating whether it has been read or not.

#### Chats
``get_chats`` - Reatime check of users's chat list.

``update_chat`` - Handle function "delete chat" on client.

## P.S
Don't use this project for real tasks. It's just test bench for learning and fun. 
