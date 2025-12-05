# Squid Game Grid

A simple web representation of the Squid Game Grid.

[The demo can be found here](https://andhw.github.io/squid-game-grid/).

Designed to be responsive.

Just a POC, the code is not very nelegant and disregarded broswer compatibility.

## Config

See [main.js](main.js) to set the `DEFAULT_NUM_OF_PLAYERS`.

You may also upload a `config.json` file in the following format:

```json
{
    "players": [
        {
            "number": 1,
            "picUrl": "456.webp"
        },
    ]
}
```

Only 1 to 100 are tested.

## Custom photos

Use the **Upload custom photos** control in the top-left corner of the page to pick one image per participant. The game will instantly rebuild the grid using your selected images (numbers are assigned in the order you select the files).

## Testing locally

Because the page fetches `config.json`, you need to serve the files over HTTP instead of opening `index.html` directly from the filesystem. A quick way to do this is with the built-in Python server:

```bash
python -m http.server 8000
```

Then visit <http://localhost:8000/> in your browser. From there you can:

- Verify the default grid renders and you can manually eliminate participants by clicking squares.
- Click the **Upload custom photos** control and select images to confirm the grid rebuilds with your files.
- Optionally drop a `config.json` (in the format above) into the project directory and refresh to ensure the configured players load.

## Handy debugging commands

```js
[...document.querySelectorAll(".square:not(.gone, .empty)")].slice(0,-1).forEach((e)=>e.click());
```

## Ideas

- Save the state of the game to a cookie.
- Add squid game geometric shaped buttons (reset the game, toggle fullscreen, etc).

## References

- <https://www.youtube.com/watch?v=0-Azzeh4b2g>
