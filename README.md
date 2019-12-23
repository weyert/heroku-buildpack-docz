## `heroku-buildpack-storybook`

This buildpack builds docz site using `yarn` and is meant to be used before `https://github.com/heroku/heroku-buildpack-static.git`.
We are assuming that you have a script command `docs:build`

If you are using an `app.json`, it might look something like this:

```JSON
{
  "name": "your-app-name",
  "description": "",
  "scripts": {},
  "env": {},
  "formation": {
    "web": {
      "quantity": 1,
      "size": "free"
    }
  },
  "addons": [],
  "buildpacks": [
    {
      "url": "heroku/nodejs"
    },
    {
      "url": "https://github.com/weyert/heroku-buildpack-docz.git"
    },
    {
      "url": "https://github.com/heroku/heroku-buildpack-static.git"
    }
  ]
}

```
