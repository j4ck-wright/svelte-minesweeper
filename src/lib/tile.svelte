<script lang="ts">
    export let isBomb: boolean;
    export let surroundingBombs: number;
    let hidden = true;
    let isFlagged = false;

    function onTileClick(mouseEvent: MouseEvent){
        if (!hidden) return;
        if (mouseEvent.button === 0) {
            if (isFlagged) return;
            hidden = false;
        } else if (mouseEvent.button === 2) {
            isFlagged = !isFlagged;
        }
    }
</script>

<div class="aspect-square" oncontextmenu="return false;">
   <div on:mousedown={(e) => onTileClick(e)} class="h-full z-10 cursor-pointer bg-sky-200 transition-all duration-200 hover:bg-blue-300" class:isFlagged={isFlagged} class:hidePointer={!hidden}>
    <p class="select-none relative top-1/2 -translate-y-1/2 transition-all duration-300" class:hideText={hidden}>{isBomb ? "💣": surroundingBombs}</p>
   </div>
</div>

<style>
    .hidePointer {
        cursor: default;
        background: none;
    }

    .hideText {
        opacity: 0;
    }

    .isFlagged {
        background-image: url("../flag.png");
        background-size: contain;
    }
</style>