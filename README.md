# Example: Firebase + Nextjs

Hey folks, apologies if this is too much to take in all at once; it's generally better to learn stuff incrementally.

But to show you how easy it is to get a real thing setup, here's an entire NextJS app that's hooked up to Firebase Authentication. It just requires you to setup Firebase Auth and then launch it with [ZEIT `now`.](https://zeit.co/)

If this overwhelms you, don't worry that's super normal. It's much easier than it initially appears. There's really only three things you need to learn here:

- A bit of npm; (checkout this [cheatsheet](https://gist.github.com/Flaque/df4e8676c243507cdd2a69b2c3610647))
- A little bit of React (learn this in [1h30m here](https://reactjs.org/tutorial/tutorial.html))
- The existence of Firebase (you probably already know this)

## Setting up or connect firebase

Set up Firebase:

- Create a project at the [Firebase console](https://console.firebase.google.com/).
- Get your account credentials from the Firebase console at _Project settings > Service accounts_, where you can click on _Generate new private key_ and download the credentials as a json file. It will contain keys such as `project_id`, `client_email` and `client_id`. Set them as environment variables in the `.env` file at the root of this project.
- Get your authentication credentials from the Firebase console under _Project settings > General> Your apps_ Add a new web app if you don't already have one. Under _Firebase SDK snippet_ choose _Config_ to get the configuration as JSON. It will include keys like `apiKey`, `authDomain` and `databaseUrl`. Set the appropriate environment variables in the `.env` file at the root of this project.
- Set the environment variables `SESSION_SECRET_CURRENT` and `SESSION_SECRET_PREVIOUS` in the `.env` file. (These are used by [`cookie-session`](https://github.com/expressjs/cookie-session/#secret).]

## Setup

Install it and run:

```bash
npm install
npm run dev
```

Deploy it to the cloud with [now](https://zeit.co/now) ([download](https://zeit.co/download))

```bash
now
```

After `now` successfully deploys, a URL will for your site will be displayed. Copy that URL and navigate to your Firebase project's Authentication tab. Scroll down in the page to "Authorized domains" and add that URL to the list.
