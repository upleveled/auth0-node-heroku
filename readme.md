# Auth0 + Node.js on Heroku

A starter template for server-side authentication with Node.js using Auth0 (deployable to Heroku).

Based off of [the official Auth0 Node.js Web App Sample](https://github.com/auth0-samples/auth0-nodejs-webapp-sample).

## Set up Auth0

Setup for Auth0 is fast and easy:

1. [Sign up for a free account at Auth0](https://auth0.com/), go to [the Dashboard](https://manage.auth0.com) and hit the **Create** button:
   ![Auth0 Dashboard](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/01-auth0.png)
2. Create an application with the "Regular Web Application" template:
   ![Create Regular Web Application](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/02-auth0.png)
3. Go to the **Settings** tab and make a note of the **Domain**, **Client ID** and **Client Secret**. This information will be used for the Heroku setup.
   ![Settings tab for application](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/03-auth0.png)

## Set up Heroku

Create a Heroku account at [Heroku - Sign up](https://signup.heroku.com/), and then click on this button:

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/upleveled/auth0-node-heroku)

This will set up a new application on your Heroku account using this repo as a template.

Choose your own app name, and use it in the `AUTH0_CALLBACK_URL` field.

During setup you'll also be asked for some other environment variables, which is the information that we noted earlier in the Auth0 setup:

![Fill in Heroku environment variables](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/04-heroku.png)

After Heroku is set up, return to the Auth0 Settings page and enter the URL in the Allowed urls (replace **YOUR-APP** with the **App name** that you chose):

1. Enter your **Allowed Callback URLs**:
   ```
   http://localhost:3000/callback,https://YOUR-APP.herokuapp.com/callback
   ```
2. Enter your **Allowed Logout URLs**:
   ```
   http://localhost:3000,https://YOUR-APP.herokuapp.com
   ```

It should appear like this:

![Auth0 Callback URLs Configuration](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/05-auth0.png)
![Auth0 Save Changes](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/06-auth0.png)

Now everything should be set up! If you go to the application, it should allow you to register and log in to view your account details:

### Homepage

![App homepage](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/07-app.png)

### Login

![App login](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/08-app.png)

### View User Details

![App user details](https://raw.githubusercontent.com/upleveled/auth0-node-heroku/master/.readme/09-app.png)

## Run the Server Locally

If you want to run the server locally, you can do this as follows:

Install the dependencies.

```sh
npm install
```

Copy the contents of `.env.example` to a new file called `.env` and replace the values for `AUTH0_DOMAIN`, `AUTH0_CLIENT_ID`, and `AUTH0_CLIENT_SECRET` with your Auth0 information (from the Settings page). Replace `EXPRESS_SESSION_SECRET` with a secret to be used for the session.

```sh
# Copy configuration to replace with your own information
cp .env.example .env
```

Run the app.

```sh
npm start
```

The app will be served at `localhost:3000`.
