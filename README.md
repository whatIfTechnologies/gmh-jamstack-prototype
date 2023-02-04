# Global Methane Hub Website Tech Stack Prototype
This repository contains proof of concept setup for the ch4pathways.org website.

This prototype is based on [this blog](https://www.pixelhop.io/writing/creating-an-internationalised-site-with-strapi-and-nuxt/).

## Some important caveats!!!

* this contains in effect 2 repositories in 1.  They would normally be separate projects.
    * [strapi](https://strapi.io/) headless cms
    * [nuxt](https://nuxt.com/) vue app
* neither of the versions in this prototype are the latest versions. I just grabbed a sample repo to get things up and running quickly for this POC. Actual development plan would be to use newer versions of both libraries along with a front-end component framework like [vuetify](https://next.vuetifyjs.com/en/).

This repo *should* include the cms content including:
* content types (`/strapi/src/api`)
* file uploads (`/strapi/public/uploads`)
* sqlite database (`/strapi/.tmp`)

*However*, it's possible that the sqlite database needs to be properly created separately using the strapi quickstart.

## Running the demo architecture

1. navigate to strapi folder and install
```
cd strapi
npm install
```
2. start strapi
```
npm run start
```

3. navigate to [localhost:1337](http://localhost:1337) in your browser to access strapi administration
4. login with credentials: username: `noah@ssg.coop` password: `xJ8@ab&MQ&fA`
5. keep strapi running and open a 2nd terminal
6. navigate to nuxt-app folder and install
```
cd nuxt-app
npm install
```
7. run nuxt server
```
npm run dev
```
8. navigate to [localhost:3000](http://localhost:3000/) in your browser to see the front-end site


Modify content and content types in strapi.

Modify the website in vue/nuxt at 
```
/nuxt-app/src/pages/index.vue
/nuxt-app/src/components/LocalSwitcher.vue
```