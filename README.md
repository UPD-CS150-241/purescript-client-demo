# purescript-client-demo

This repository demonstrates how the parts of the [`cs150241project-lib`](https://github.com/UPD-CS150-241/cs150241project-lib/t) package can be used to create a Canvas-based application with networking.

## Setup

1. If you do not have `spago@next` installed yet, first uninstall the regular `spago` via `npm uninstall -g spago`, then run `npm install -g spago@next`
1. Run `spago install cs150241project-lib` while in the repository root to install the `cs150241project-lib` library
1. Run `spago bundle --outfile web/index.js` while in the repository root to bundle the demo code into a single JavaScript file
1. Open `web/index.html` in your browser to start the application

## Details

The demo code does the following:

- On startup:
    - Connects to `localhost:15000` _(i.e., the default values for a Go-based communication server instance running on your computer)_
    - Loads `umbreon.png` for use
    - Sets FPS to `60`
    - Sets the game canvas to 500px x 500px
- After every frame:
    - Increments the number of ticks by `1`
- Every 60 frames:
    - Shows `umbreon.png` in a random location within the game canvas
    - Sends a message to the server containing the new coordinates
- On key down:
    - Sends a message to the server containing the pressed key
- On mouse click:
    - Sends a message to the server containing the coordinates of the mouse click
- On message received:
    - Shows the received message at the center of the game canvas _(if connected)_
