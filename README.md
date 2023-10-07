# Window maker 3000

This is a very small npm package for creating draggable windows on a webpage.

Right now this is only a svlete package but svelte is a compiler so it can be compiled to vanilla js as well.

## Usage

1. `npm install window-maker`

2. `import { WindowConstructor } from 'window-maker'`

3. `<WindowConstructor>
        <your content here>
    </WindowConstructor>`

    make sure to have a wrapper inside the WindowConstructor with id `window-body` and an element in it with the id `window-head` 

    the `window-body` is the whole part that moves and the `window-head` is the draggable part

    any other content can be in any of those elements

    example:

    ```html
    <WindowConstructor>
        <div id="window-body">
            <div id="window-head">this is a the window head</div>
            <div>this is the window content</div>
        </div>
    </WindowConstructor>
    ```

        