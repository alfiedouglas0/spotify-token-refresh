# spotify-token-refresh

Due to the design of OAUTH2, which is used by the spotify api, each user access token will expire after 1 hour - meaning the user will need to login again unless you implement the [Authorization Code Flow](https://developer.spotify.com/documentation/general/guides/authorization-guide/).

This repository uses the code from the [example server](https://github.com/lufinkey/react-native-spotify/tree/master/example-server) in the [react-native-spotify](https://github.com/lufinkey/react-native-spotify) repository, and is suitable to be deployed in a click:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/alfiedouglas0/spotify-token-refresh)

This will require you to enter:

* `SPOTIFY_CLIENT_ID` - Your spotify app id, found the spotify developer dashboard
* `SPOTIFY_CLIENT_SECRET` - Your spotify client secret, found the spotify developer dashboard
* `SPOTIFY_CLIENT_CALLBACK` - Your spotify app redirect URL, found the spotify developer dashboard
* `ENCRYPTION_SECRET` - Any arbitrary string to use to encrypt/decrypt refresh tokens

which can all be found in the [spotify developer dashboard](https://developer.spotify.com/dashboard/).

This will set up a server that will run for free! The only issue being that if the server has been inactive for over 30 minutes it will go to sleep, the only way I have found to get around this is to set up a service to ping your server every 5 minutes or so.