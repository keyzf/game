<p align="center">
  <img src="https://github.com/Navarra/game/raw/master/src/assets/logo.png"/>
</p>

<p align="center">
  <a href="https://gitter.im/Navarra/game"><img src="https://badges.gitter.im/Navarra/game.svg" alt="gitter.im"></a>
  <a href="https://circleci.com/gh/Navarra/game/tree/master"><img src="https://circleci.com/gh/Navarra/game/tree/master.svg?style=svg" alt="circleci"></a>
</p>

<p align="center">
  <strong>Welcome to Navarra. An online, 2D medieval game using JavaScript and HTML5.</strong>

  <img width="704" alt="Game screenshot" src="https://user-images.githubusercontent.com/616320/34860792-9a2c0ee8-f725-11e7-9e60-91b8610926f2.png">
</p>

## Getting Started

> You can view a video-tutorial of this getting started guide [located here](https://www.youtube.com/watch?v=5a69TEEJ-oY).

### 1. Website

First, using your terminal or Sequel Pro or PHPMyAdmin, create your `MySQL` database. Easy peasy.

Secondly, in your terminal, make a new directory called `navarra` and type the following:

      $ git clone https://github.com/Navarra/website
      $ cp .env.example .env

Then, let's edit the `.env` file we just created from our last command (`cp`) and put in the database credentials.

Now, let's make the website. In your terminal, at `/navarra/website/`, type:

      $ composer install
      $ php artisan jwt:secret
      $ php artisan key:generate
      $ php artisan migrate
      $ php artisan config:cache
      $ npm install
      $ npm dev

Your website's CSS should now be compiled and your database's tables should now be created. Also, your secret JWT authentication key was created along with the Laravel application key.

Time to make your player! Let's serve up the website:

      $ php artisan serve

Now go to `https://localhost:8000` and register your player account. You are all set!

### 2. Game

Go to `/navarra` and now type the following, in your terminal:

      $ git clone https://github.com/Navarra/game
      $ cd game
      $ npm install
      $ npm run dev

You should now have two folders under `navarra`:

    navarra/
    ├── game/
    └── website/

Now go inside `game`'s `package.json ` file and fill out the `SITE_URL` with the URL of the website you setup previously inside the `nodemonConfig` object near the bottom.

Now, you can start the Node.js server by typing `npm run ndb` and then starting the `dev_server` script on the left-hand side.

> This will start the server within ndb and you will have an easy time debugging and seeing everything.

Now you may visit `http://localhost:8080` to login to the game using your newly-created player.

## Contributing

Please check out our [CONTRIBUTING.md](https://github.com/Navarra/game/blob/master/CONTRIBUTING.md) guide on how you can actively participate in the development of this medieval game. It's pretty easy and fun!

## Systems and Engines

Here are the types of things I will be adding as a minimum viable product (alpha). Not too over the top but enough to cover the basics until more is added. Each section links to a project which will contain its sub-tasks within.

### What does a checkmark mean?

When an item is checkmarked, it means the basic foundation is in place. Sometimes, however, it is not fully complete. For example, Inventory is checkmarked but the inventory currently only supports weapons. You cna help fix that.

- [Player](https://github.com/Navarra/game/projects/1)
  - [x] Walking / pathfinding
  - [ ] Context-menu / Actions*
  - [ ] Health and stats
  - [ ] Inventory*
  - [ ] Character wear*
  - [ ] Your first quest
- [User Interface](https://github.com/Navarra/game/projects/2)
  - [x] Inventory tab
  - [ ] Quests tab
  - [x] Chatbox (for players and actions)
  - [x] Character wear tab
  - [x] Overall look &amp; feel
- [NPC](https://github.com/Navarra/game/projects/3)
  - [ ] Trading
  - [x] Walking around
  - [x] Talking
  - [ ] Examine
- [Monsters](https://github.com/Navarra/game/projects/3)
  - [ ] Battle System
  - [ ] Looting
  - [ ] Spawning
- [Networking](https://github.com/Navarra/game/projects/5)
  - [X] Player connect to server
  - [X] Non-playable characters
  - [ ] Monsters
  - [X] Items
  - [ ] Minor networking tweaks / alpha-stage

> Items marked with an asterisk (*) are started but have not been finalized or finished.

Once all of these items are checked, Navarra will be stable without breaking changes.

## Debugging

Learning how to debug in this game is critical in order to interact with the Node.js server and to the client. Your primary source should be the [ndb](https://github.com/GoogleChromeLabs/ndb) tool from Google. It is an improved debugging experience witch __drastically__ improved client-side debugging.

Read more at [DEBUGGING.md](debugging.md).

## Why are you making yet another game?

I've been wanting to make a Medieval-themed game for a while now with a old-school feel. Also, I wanted it to be multiplayer where players can connect and see each other. Maybe you want to train Mining and then maybe later Smithing? Yep. A neat PvE system? Yep.

An open-source environment, I hope, cultivates learning, sharing and developing together the world of Navarra. The lore and history, much of to be written, will drive this game.

I also hope to learn on topics such as collaboration (in an open-source world) where I develop my own DevOps skills wherein project standards are not only made but kept through the power of CI/CD.

Lastly, this game will give me a great reason to try out `D3` and make cool data viz graphs in the `Navarra/website` section. You want to see cool graphs regarding your player? You're gonna get it. Or you can help contribute!

## Notice

Navarra contains work from multiple sources not organically made by contributions from Navarra directly.

- [Tileset, monsters, items, players](http://pousse.rapiere.free.fr/tome/tome-tiles.htm) by David E. Gervais. &middot; [CC license](https://creativecommons.org/licenses/by/3.0/)
- [Main screen music](https://opengameart.org/content/enchanted-festival) by [Matthew Pablo](http://www.matthewpablo.com). &middot; [CC license](https://creativecommons.org/licenses/by/3.0/)
- Game font '[PixelMix](https://www.dafont.com/pixelmix.font)' by [Andrew Tyler](http://andrewtyler.net/fonts/), IBM VGA8 by IBM.
- [Heroicons](https://github.com/sschoger/heroicons-ui) by [Steve Schoger](http://www.steveschoger.com/)
