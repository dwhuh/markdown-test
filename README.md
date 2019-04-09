Markdown Test
=============

## Management.js
```
class Management {
  users = [];
  chattings = [];

  insertUser(user, socket) {
    this.users.push({ ...user, socket });
  }

  findUserById(id) {
    return this.users.find(a => a.id === id);
  }

  getUserData() {
    return this.users;
  }

  getUserList() {
    return this.users.map((user) => ({
      ...user, socket: null,
    }));
  }
}
```

## User.js
```
class User {
  constructor(socket = null, id = '', name = '', isLoggedin = false, isForceLogout = false) {
    this.id = id;
    this.name = name;
    this.isLoggedin = isLoggedin;
    this.isForceLogout = isForceLogout;
    this.socket = socket;
    this.key = Date.now();
    this.createdAt = Date.now();
  }
}
```

## Chatting.js
```
class Chatting {
  constructor(socket = null) {
    this.socket = socket;
    // ['John', 'Marry', 'Ryan',]...
    this.entries = [];
    // ['Ryan',]...
    this.waites = [];
    // { createdAt, message, id }
    this.messages = [];
    this.createdAt = Date.now();
    this.updatedAt = Date.now();
  }
}
```
