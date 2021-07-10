# Baumbot

A (very) simple Discord bot intended to run on AWS Lambda written in Node with TypeScript.

## Prerequisites

- Node 14

## Running locally

### Install dependencies

```sh
npm i
```

### Setup required environment variables

Create a `.env` file at the root of the project:
```
AUTHORIZATION_HEADER=<Bot token from Discord>
CHANNEL_ID=<Discord channel id>
```

## Build the project
```sh
npm run build
```

Note: This project does not currently live reload. You will need to rebuild everytime you make a change.

### Run the bot
```sh
npm run dev
```

A message should be posted to the Discord channel defined in your environment variables.

## Deploying to Lambda

### Build the project
```sh
npm run build
```

A zipped function should be output to `dist/dist.zip`.

### Upload to Lambda

Within your Lambda in the AWS Console select `Upload from` -> `.zip file`.

### Configure environment variables

Within your Lambda in the AWS console go to `Configuration` and configure the required environment variables:
- `AUTHORIZATION_HEADER`
- `CHANNEL_ID`