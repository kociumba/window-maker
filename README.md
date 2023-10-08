# Window maker

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

# Updates

> new for 0.0.4:
> 1. added `className` prop to the component to apply custom classes to the wrapper element
> 2. foxed issues with z-index where the windows below would not be draggable (this is a temporary fix for now but it works ig)

---

> new for 0.0.3:
> 1. won't break if you use more than one component instance on the same page 😎
