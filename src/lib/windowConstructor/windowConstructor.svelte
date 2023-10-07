<script>
    import { onMount } from "svelte";
    export const ssr = false;

    function assignUniqueIds() {
        const windowHeads = document.querySelectorAll(".window-head");
        const windowBodies = document.querySelectorAll(".window-body");

        windowHeads.forEach((windowHead, index) => {
            windowHead.id = `window-head-${index}`;
        });

        windowBodies.forEach((windowBody, index) => {
            windowBody.id = `window-body-${index}`;
        });
    }

    function windowConstructor() {
        const windowHeads = document.querySelectorAll(".window-head");

        windowHeads.forEach((currentWindowHead) => {
            const index = currentWindowHead.id.split("-")[2];
            const windowBody = document.getElementById(`window-body-${index}`);

            windowBody.style.position = "absolute";
            windowBody.style.top = "0";
            windowBody.style.left = "0";

            let isDragging = false;
            let offsetX = 0;
            let offsetY = 0;

            currentWindowHead.addEventListener("mousedown", startDrag);
            currentWindowHead.addEventListener("mousemove", drag);
            currentWindowHead.addEventListener("mouseup", stopDrag);

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
        });
    }

    let windowHead;
    let windowBody;

    onMount(() => {
        assignUniqueIds();

        // windowHead = document.getElementById("window-head");
        // windowBody = document.getElementById("window-body");

        // windowBody.style.position = "absolute";
        // windowBody.style.top = "0";
        // windowBody.style.left = "0";

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
