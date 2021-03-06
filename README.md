# Game dev on JavaScript (frontend + backend, dev stage, desktop version)

This is dev branch of the final RSS-2019 project. 

## Detailed structure of the app

The initial task was: build game web-app for children using only JavaScript (frontend) and nodejs (backend). Use of any js-frameworks is forbidden.
A user is expected to play against a monster generated by the generateMonster function. Initially, the user is given 100 health points and the ability to choose a task via modal dialog. 
In case of a correct answer to the task the user is given the opportunity to choose the spell against the monster, in case of defeat (wrong answer) 25 health points are taken away. 
The game ends when health points are 0. The user can quit the game at any time by pressing the Escape button.

**Frontend**

First of all frontend part is a multipage app, so the structure is as follows:

- Main windows (screens):
  - Home page: shows game rules
  - Score page: shows the latest users and their scores
  - Login page: sign in/sign up
  - Battle page: 
- Modal dilalog:
  - Pops up when selecting a spell (=task)
  - 9 different tasks in total
  - Several different visual effects and audio track of a spell

**Backend**

As far as backend two services were created with docker compose: the first one is a web API written on nodejs, the second one is a database.
MongoDB was used for storing users and their scores.

- MongoDB service
- Nodejs service 

### Game rules

All information related to this game can be found on the main page of the app (index.html)

### Screenshots

These are some screenshots of an active window:

![The main battle window](https://imgur.com/0C8WoRl)
![Modal dialog](https://imgur.com/L3T2Gja)
![Task "Listening"](https://imgur.com/lF2DbVQ)
![Task "Ordering"](https://imgur.com/xyyDrfn)
![Task "Translation"](https://imgur.com/ZVnte1W)
![Task "Biology"](https://imgur.com/zzVGgZr)

## Run locally

1. Set some environment variables (username and password) for access to the MongoDB database.

```bash
export MONGODB_USER="your username"
export MONGODB_PASS="your password"
```

Lately those environement variables will be deleted.

2. From project directory start up backend by running `docker-compose up`:

```bash
docker-compose up
```

Backend part of the app is now running on http://127.0.0.1:4000

3. For the frontend part of the app a bundle must be built via webpack:

```bash
npm build
```

The "distribution" code is now located in `./dist`. Open `index.html` file in `./dist` directory and load it in the browser (e.g. via `Live Server`).