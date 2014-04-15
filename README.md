Real-time web-based collaborative coding

pairjam.com

** Actual documentation and instructions coming soon! **

## Features
- Syntax highlighting code editor (using Ace)
- Live edit merging via operational transforms
- Load files from GitHub repositories
- Audio and video through WebRTC

## Design overview

Pairjam is designed with strong separation between the client and server.

The client consists solely of static files, which means it can be served quickly
and cheaply on a CDN (pairjam.com assets are hosted on GitHub pages).

The server is a Node.js WebSocket server that can run on one or more separate machines.

### Client

### Server

#### GitHub integration

In order to integrate the server with GitHub, a GitHub API public key
and secret are needed. These should be placed in a file called github_api_secret in
the /server directory, with the following form:

```javascript
module.exports = {
	'client_id' : 'YOUR CLIENT ID',
	'client_secret' : 'YOUR CLIENT SECRET'
};
```

If the server does not find this file upon loading, rate requests will be limited to
GitHub's unauthenticated limit.
