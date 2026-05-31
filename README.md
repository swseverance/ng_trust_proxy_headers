# NgTrustProxyHeaders

Deploy this app to Firebase App Hosting to view the warning logs regarding x-forwarded- headers

## Installation

### 1. Install Node.js

This project requires **Node.js 22 LTS** (minimum Node 20.9).

The recommended way is via [nvm](https://github.com/nvm-sh/nvm):

```bash
nvm install 22
nvm use 22
```

Or download directly from [nodejs.org](https://nodejs.org).

### 2. Install dependencies

```bash
npm install
```

## Deployment

Reproducing the issue requires deploying to Firebase App Hosting.

### Install the Firebase CLI

```bash
npm install -g firebase-tools
```

### Authenticate

```bash
firebase login
```

### Configure your Firebase project

Update `.firebaserc` to point to your own Firebase project:

```json
{
  "projects": {
    "default": "your-firebase-project-id"
  }
}
```

### Create an App Hosting backend

```bash
firebase apphosting:backends:create
```

Then update `firebase.json` with the backend ID that was created:

```json
{
  "apphosting": {
    "backendId": "your-backend-id",
    ...
  }
}
```

### Deploy

```bash
firebase deploy
```