<script>
    import WindowConstructor from "/src/lib/WindowConstructor/WindowConstructor.svelte";

    // function copyCode() {
    //     navigator.clipboard.writeText("npm install window-maker")
    //         .then(() => {
    //             console.log("Text copied to clipboard");
    //         })
    //         .catch((error) => {
    //             console.error("Error copying text to clipboard:", error);
    //         });
    // }
</script>

<svelte:head>
    <title>Window Maker</title>
    <meta name="description" content="Window Maker" />
</svelte:head>

<main>
    <WindowConstructor className="window1">
        <div class="window-body one" id="window-body">
            <div class="window-head head" id="window-head">
                these windows are draggable !!
            </div>
            <div class="content">
                $HOME> this is a demo for my <a
                    class="gradient"
                    href="https://github.com/kociumba/window-maker"
                    >window maker</a
                >
                package
                <br />
                <img
                    class="content boar"
                    src="https://i.imgflip.com/6u41fb.png"
                    alt="mind blown boar"
                />
            </div>
        </div>
    </WindowConstructor>
    <WindowConstructor className="window2">
        <div class="window-body two" id="window-body">
            <div class="window-head head" id="window-head">
                "I love this web window manager" - a happy customer
            </div>
            <div class="content">
                $HOME> don't wait get it now and start writing windows(web
                version)
                <br />
                $GITHUB> get it on github:
                <a
                    class="gradient"
                    href="https://github.com/kociumba/window-maker"
                    style="font-weight: bold;"
                    >HERE !!!
                </a>
                <br />
                $NPM> or just npm it into your svelte project with
                <button class="code">npm install window-maker</button>
                <br />
                <img 
                    class="content cow"
                    src="https://media.tenor.com/ezRuC2ke2jMAAAAd/shannon-sharpe-suit-meme.gif" 
                    alt="cow" 
                />
            </div>
        </div>
    </WindowConstructor>
    <WindowConstructor className="window3">
        <div class="window-body three" id="window-body">
            <div class="window-head head" id="window-head">
                funny spiral thing
            </div>
            <div class="content spiral">
                <img
                    class="content spiral"
                    src="https://media0.giphy.com/media/WPor8AxNoe3Yv0H6xm/giphy-downsized-large.gif?cid=6c09b9525v0hrgdh45j9q3xqyigx1p2q6tlemac10al1lfs6&ep=v1_internal_gif_by_id&rid=giphy-downsized-large.gif&ct=g"
                    alt="mind blown boar"
                />
            </div>
        </div>
    </WindowConstructor>
    <WindowConstructor className="window4">
        <div class="window-body four" id="window-body">
            <div class="window-head head" id="window-head">
                devs when they use&nbsp; <span class="gradient"> window maker</span>
            </div>
            <div class="content spiral">
                <img 
                    class="content neuron"
                    src="https://media.tenor.com/VbbSQLP4g0cAAAAC/neuron-activation.gif" 
                    alt="neuron activation"
                />
            </div>
        </div>
    </WindowConstructor>
    <footer>
        <div class="social-icons">
            <a
                href="https://github.com/kociumba"
                target="_blank"
                rel="noopener noreferrer"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    ><path
                        d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                    /></svg
                >
            </a>
            <a
                href="https://twitter.com/kociumba"
                target="_blank"
                rel="noopener noreferrer"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    ><path
                        d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
                    /></svg
                >
            </a>
        </div>
        <div class="copyright">
            <p>© 2023 kociumba</p>
        </div>
    </footer>
</main>

<style>
    ::selection {
        background-color: #ffffff;
        color: #000000;
    }

    svg {
        fill: #ffffff;
        height: 30px;
        width: 30px;
    }

    :global(body) {
        background-color: #1e1e1e;
        background-image: linear-gradient(to right, #0c0608, #09040c);
        color: #ffffff;
        font-family: Consolas, monospace;
        overflow: hidden;
    }

    .window-body {
        display: flex;
        flex-direction: column;
        width: 40vw;
        height: 50vh;
        background-color: #333333;
        border: 1px solid #555555;
        border-radius: 5px;
        overflow: hidden;
        font-family: Consolas, monospace;
    }

    .head {
        height: 30px;
        padding: 5px;
    }

    .one {
        transform: translate(5vw, 6vh);
        display: block;
    }

    .two {
        transform: translate(52vw, 39vh);
    }

    .three {
        transform: translate(68vw, 9vh);
        width: 200px;
        height: 210px;
        display: block;
    }

    .four {
        transform: translate(10vw, 65vh);
        display: block;
        width: 400px;
        height: 190px;
    }

    .head {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 30px;
        background-color: #333333;
        color: #ffffff;
        font-weight: bold;
        font-size: 17px;
    }

    .content {
        flex: 1;
        padding: 10px;
        background-color: #1e1e1e;
        color: #ffffff;
        font-size: 17px;
        border: none;
    }

    .boar {
        width: 40vw;
        height: 40vh;
    }

    .code {
        display: inline-block;
        padding: 2px 4px;
        background-color: #000000;
        color: #ffffff;
        font-family: Consolas, monospace;
        font-size: 17px;
        font-weight: bold;
        border: none;
        border-radius: 4px;
    }

    .spiral {
        padding: 0px;
        height: 200px;
        width: 200px;
    }

    .neuron {
        padding: 0px;
        height: 150px;
        width: 400px;
    }

    .cow {
        padding: 0px;
        padding-top: 15px;
        height: 35vh;
        width: 39vw;
        border-radius: 10px;
    }

    .gradient {
        position: relative;
        display: inline-block;
        text-decoration: underline;
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        background-image: linear-gradient(to right, #ff0055, #a333ff);
        font-weight: bold;
    }

    footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center; /* Updated */
    padding: 10px 20px; /* Updated */
    box-sizing: border-box; /* Added */
  }

  .social-icons {
    display: flex;
    gap: 10px;
    z-index: 2;
    flex: 1; /* Added */
  }

  .copyright {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    flex: 1; /* Added */
  }

</style>
