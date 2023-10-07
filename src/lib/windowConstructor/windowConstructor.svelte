<script>
    // export let WindowConstructor
    import { onMount } from "svelte";
    export const ssr = false;

    function windowConstructor() {
        // const windowHead = document.getElementById("window-head");
        // const windowBody = document.getElementById("window-body");

        let isDragging = false;
        let offsetX = 0;
        let offsetY = 0;

        windowHead.addEventListener("mousedown", startDrag);
        windowHead.addEventListener("mousemove", drag);
        windowHead.addEventListener("mouseup", stopDrag);

        function startDrag(event) {
            isDragging = true;
            offsetX =
                event.clientX - parseInt(getComputedStyle(windowBody).left);
            offsetY =
                event.clientY - parseInt(getComputedStyle(windowBody).top);
        }

        function drag(event) {
            if (isDragging) {
                const x = event.clientX - offsetX;
                const y = event.clientY - offsetY;
                windowBody.style.left = `${x}px`;
                windowBody.style.top = `${y}px`;
            }
        }

        function stopDrag() {
            isDragging = false;
        }
    }

    let windowHead;
    let windowBody;

    onMount(() => {
        windowHead = document.getElementById("window-head");
        windowBody = document.getElementById("window-body");

        windowBody.style.position = "absolute";
        windowBody.style.top = "0";
        windowBody.style.left = "0";

        //   windowHead.addEventListener("mousedown", startDrag);
        //   windowHead.addEventListener("mousemove", drag);
        //   windowHead.addEventListener("mouseup", stopDrag);

        windowConstructor();
    });
</script>

<div class="body">
        <slot />
</div>

<!-- <style>
    .body {
        position: absolute;
        top: 0;
        left: 0;
    }
</style> -->
