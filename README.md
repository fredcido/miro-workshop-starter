# Miro Workshop: React 18 + Server Components

This sample app demonstrates the use of the Miro REST API and OAuth authorization. This app is based on the Next.js 12 React Server Components Demo app and includes both react server and react client components. We’ve created our own project based on this, and added the Miro OAuth flow to be included in some boilerplate functionality.

React capabilities covered in this sample app:

1. [x] React client components
2. [x] React server components

Miro capabilities covered in this sample app:

1. [x] Miro OAuth
2. [x] Miro REST API

## Stack

- [x] React 18
- [x] Next JS
- [x] Axios
- [x] Miro REST API
- [x] Mirotone (styling)

## Workshop Resources

- [x] [Developer Documentation](https://developers.miro.com/)
- [x] [Mirotone documentation](https://www.mirotone.xyz/)
- [x] [Discord Server](bit.ly/miro-developers)

## Prerequisites

1. Create a [developer team in Miro](https://miro.com/app/dashboard/?createDevTeam=1)
2. Create an [app in Miro](https://miro.com/app/settings/user-profile/apps)
3. Create a board in Miro that you'd like to manipulate using our REST API
4. Open up our [Discord Server](bit.ly/miro-developers) to see code snippets, ask questions, etc.

## How to start

First, make sure you've handled the prerequisites in full:

- Create a [developer team in Miro](https://miro.com/app/dashboard/?createDevTeam=1)
  - Click the link above, to create a developer team under your account
- Create an [app in Miro](https://miro.com/app/settings/user-profile/apps)
  - From your developer team in Miro, click the "Build Apps" button in the team dashboard UI
  - Name your app, click 'create'
  - Scroll down to 'App Credentials' and copy the client id and client secret — we will use these below in step 4
  - Continue to scroll down to 'Redirect URI for OAuth2.0' and paste in the following redirect url: `http://localhost:3000/api/redirect/`
  - Lastly, scroll down to 'Permissions' and check off the `Board:Read` and `Board:Write` scopes
- Navigate back to your developer team dashboard and create a new board in Miro. Make note of the board ID in the URL of the new board — we will use this below in step 5

Next, we can start working directly with this sample app:

1. Clone or download repo
2. `cd` to root folder
3. Run `yarn install` to install dependencies.
4. Create a .env file in the root folder, and set the following variables:

```
clientID={YOUR_CLIENT_ID)
clientSecret={YOUR_CLIENT_SECRET}
redirectURL=http://localhost:3000/api/redirect/
```

5. Navigate to `constants.js` and add the `boardId` of the Miro Board you'd like to leverage/modify
6. Run `yarn dev` to start the local server

Once your server is up and running, navigate to `http://localhost:3000/` in your browser. If the project is running successfully, you should see a 'Sign in' button in the UI.

## Folder Structure

```
.
├── package.json <-- The dependencies for the app
└── next.config.js <-- Configuration file for Next JS
└── constants.js <-- Houses isolated variables (Miro board ID)
└── .env <-- File you will create, where you store your sensitive credentials (Client ID, Secret)
└── node_modules <-- Node modules that are installed based on dependencies
└── components
      └── Input.js <-- client component
      └── MiroItem.js <-- client component
      └── Time.server.js <-- server component
└── pages
        └── api
            └── authenticate.js <-- check user auth status
            └── getItems.js <-- call Miro API to retrieve board items
            └── redirect.js <-- handle redirect after successful authorization
            └── signin.js <-- handle oauth authorization
            └── updateContent.js <-- call Miro API to update sticky note content
    └── _app.js <-- main app.js file for Next JS app
    └── _document.js <-- Next JS import file
    └── index.server.js <-- root server file for app
    └── main.client.js <-- root client file for app
└── public
└── styles

```

---

The finished version of this workshop can be found [here](https://github.com/miroapp/miro-workshop-finished).
