<script>
    import WindowConstructor from "/src/lib/WindowConstructor/WindowConstructor.svelte";
</script>

<main>
    <WindowConstructor className="window">
        <div class="window-body" id="window-body"> 
            <div class="window-head" id="window-head">this is a the window head</div>
            <div class="content">this is window text</div>
        </div>
    </WindowConstructor>
    <WindowConstructor className="window">
        <div class="window-body" id="window-body"> 
            <div class="window-head" id="window-head">fuck</div>
            <div class="content">you</div>
        </div>
    </WindowConstructor>
</main>

<style>

    .window-head {
        background-color: red;
        width: 50vw;
    }

    .content {
        background-color: blue;
    }

</style>
