# TCP File Transfer Lab

An educational file-transfer project with a **Node.js TCP server** and an **Electron desktop client**. The server uses a custom command protocol over sockets; it is not a standards-compliant FTP server.

## Components

| Directory | Purpose |
| --- | --- |
| [Server-FTP/](Server-FTP/) | TCP server, command dispatch, and filesystem operations. |
| [Client-FTP/](Client-FTP/) | Electron client and connection handling. |

The original directory names are retained so existing paths and scripts continue to resolve.

## Run locally

Use Node.js and npm. Neither package pins a Node.js version; the Electron client depends on older tooling.

Start the server from its own directory:

```sh
cd Server-FTP
node index.js
```

In another terminal, install and start the desktop client:

```sh
cd Client-FTP
npm ci
npm start
```

Review the connection settings in [Client-FTP/main.js](Client-FTP/main.js) and the listener in [Server-FTP/index.js](Server-FTP/index.js) before connecting. The client also provides `npm run dev`, which runs Electron through nodemon.

## Development notes

- Each component has its own `package.json`.
- The server has no `start` script; invoke `node index.js` explicitly.
- Both `test` scripts are placeholders, not test suites.
- File-transfer commands modify local files. Use disposable test directories when exploring the protocol.
- Input validation and protocol handling need further review before the server is exposed to a network. No end-to-end transfer test was performed during this documentation update.
