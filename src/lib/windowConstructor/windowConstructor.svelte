<script>
    import { onMount } from "svelte";
    import { writable } from "svelte/store";
    export let className;
    // export let boxShadow = false;
    export const ssr = false;
    const draggedWindows = writable([]);

    function assignUniqueIds() {
        const windowHeads = document.querySelectorAll(".window-head");
        const windowBodies = document.querySelectorAll(".window-body");
        // const windows = document.querySelectorAll(className);  // TODO: fix the z fighting and box shadow implementation
        // let focusedWindowIndex = -1;

        windowHeads.forEach((windowHead, index) => {
            windowHead.id = `window-head-${index}`;

            // if (windowHead.classList.contains("focused")) {
            //     focusedWindowIndex = index;
            // }
        });

        windowBodies.forEach((windowBody, index) => {
            windowBody.id = `window-body-${index}`;
        });

        // windows.forEach((Dwindow, index) => {
        //     Dwindow.classList.remove("focused");

        //     if (index === focusedWindowIndex) {
        //         Dwindow.classList.add("focused");
        //         if (boxShadow) {
        //             Dwindow.style.boxShadow = "0px 0px 10px black";
        //         } else {
        //             Dwindow.style.boxShadow = "none";
        //         }
        //     } else {
        //         Dwindow.style.boxShadow = "none";
        //     }
        // });
    }

    function windowConstructor() {
        const windowHeads = document.querySelectorAll(".window-head");

        draggedWindows.set(Array.from(windowHeads).map((head) => head.id.split('-')[2]));

        windowHeads.forEach((currentWindowHead) => {
            const index = currentWindowHead.id.split("-")[2];
            const windowBody = document.getElementById(`window-body-${index}`);

            console.log(index);

            // if (boxShadow && currentWindowHead.classList.contains("focused")) {
            //     windowBody.style.boxShadow = "0px 0px 10px black";
            // } else {
            //     windowBody.style.boxShadow = "none";
            // }

            windowBody.style.position = "absolute";
            windowBody.style.top = "0";
            windowBody.style.left = "0";

            let isDragging = false;
            let offsetX = 0;
            let offsetY = 0;

            if (!currentWindowHead.classList.contains("eventfull")) {
                currentWindowHead.addEventListener("mousedown", startDrag);
                currentWindowHead.addEventListener("mousemove", drag);
                currentWindowHead.addEventListener("mouseup", stopDrag);
                currentWindowHead.classList.add("eventfull");
            }

            function startDrag(event) {
                if (!isDragging) {
                    isDragging = true;
                    offsetX =
                        event.clientX -
                        parseInt(getComputedStyle(windowBody).left);
                    offsetY =
                        event.clientY -
                        parseInt(getComputedStyle(windowBody).top);

                    draggedWindows.update((windows) => windows.filter((window) => window !== index));
                    console.log(draggedWindows);
                    // updateZIndex(index);
                }
            }

            function drag(event) {
                if (isDragging) {
                    const x = event.clientX - offsetX;
                    const y = event.clientY - offsetY;
                    windowBody.style.left = `${x}px`;
                    windowBody.style.top = `${y}px`;
                    windowBody.style.zIndex = "1";

                    // const otherWindowBodies = document.querySelectorAll(`.window-body:not(#window-body-${index})`);
                    // otherWindowBodies.forEach((otherWindowBody) => {
                    //     otherWindowBody.style.zIndex = "-1";
                    // });
                }
            }

            function stopDrag() {
                isDragging = false;
                zIndexUpdated = false;
                // windowBody.style.zIndex = "-1";

                draggedWindows.update((windows) => [...windows, index]);
            }
        });
    }

    let zIndexUpdated = false;
    let allWindows = [];

    function updateZIndex(index) {              //TODO: make this work

        if (draggedWindows.includes(index)) {
            draggedWindows.splice(index, 1);
        }

        // const indexInDraggedWindows = draggedWindows.indexOf(index);
        // if (indexInDraggedWindows !== -1) {
        //     draggedWindows.splice(indexInDraggedWindows, 1);
        // }

        draggedWindows.push(index);

        if (zIndexUpdated == false) {
            // console.log(allWindows, "allWindows");
            // console.log(allWindows.length, "allWindows.length");


            zIndexUpdated = true; // Set the flag to indicate z-index has been updated
        }
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

<div class={className} id="window">
    <slot />
</div>

<!-- <style>
    .body {
        position: absolute;
        top: 0;
        left: 0;
    }
</style> -->
