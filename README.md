# chatapp
A group chat web application that can run on multiple clients on same network. Built using Node.js, Socket.io, Mongoose, Jquery, Ajax, Javascript, Handlebars, HTML and CSS.

Usage

1.    Open Chrome.
2.    Go to localhost:4000/register for new member or localhost:4000/entry for existing members.
3.    Enter the user id and email you wish to appear in the Login section.
4.    Make your friends join too on different browser (if they are on the same network).
      (NOTE:IT IS COMPULSORY TO CLICK ON THE USER YOU WANT TO SEND MESSAGE AND NOT ON YOUR OWN EMAIL ID)


Features

1.    One to one chat.
2.    Chat messages saved in mongodb.
3.    Clean UI and UX.

Database

Mongoose is used to interact with a MongoDB that's hosted by MongoLab.

Schemas

There are two schemas; users and chats.
Each user has a user id and email id.
Each chat has a title, and array of connections. Each item in the connections array represents a user connected through a unique socket; object composed of {userId + socketId}. Both of them together are unique.

Models

Each model wraps Mongoose Model object, overrides and provides some methods. There are two models; User and Chats.

Session

Session in Express applications are best managed using express-session package. Session data are stored locally on your computer, while it's stored in the database on the production environment. Session data will be deleted upon logging out.

Sockets

Having an active connection opened between the client and the server so client can send and receive data. This allows real-time communication using TCP sockets. This is made possible by Socket.io.
The client starts by connecting to the server through a socket(maybe also assigned to a specific namespace). Once connections is successful, client and server can emit and listen to events.
