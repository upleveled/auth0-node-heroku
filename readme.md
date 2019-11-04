# Auth0 + Node.js on Heroku

## Set up Auth0

Setup for Auth0 is fast and easy:

1. [Sign up for a free account at Auth0](https://auth0.com/) and [open the Dashboard](https://manage.auth0.com)
2. Create an application with the "Regular Web Application" template and go to **Settings**
3. Under the settings page, there will be the **Domain**, **Client ID** and **Client Secret**, which will be used for the Heroku setup

## Set up Heroku

Deploy this app to Heroku for free:

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/karlhorky/auth0-node-heroku)

During setup you'll be asked for some configuration variables, available on the Settings page in **Set up Auth0** above.

After Heroku is set up, note down your app URL, return to the Auth0 Settings page and enter the URL in the Allowed urls (replace **YOUR-APP** with the subdomain of your app):

1. Enter your **Allowed Callback URLs**:
   `http://localhost:3000/callback,https://YOUR-APP.herokuapp.com/callback`
2. Enter your **Allowed Logout URLs**:
   `http://localhost:3000,https://YOUR-APP.herokuapp.com`

## Run the Server Locally

Install the dependencies.

```sh
npm install
```

Rename `.env.example` to `.env` and replace the values for `AUTH0_DOMAIN`, `AUTH0_CLIENT_ID`, and `AUTH0_CLIENT_SECRET` with your Auth0 information (from the Settings page). Replace `EXPRESS_SESSION_SECRET` with a secret to be used for the session.

```sh
# Copy configuration and replace with your own information
cp .env.example .env
```

Run the app.

```sh
npm start
```

The app will be served at `localhost:3000`.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.
