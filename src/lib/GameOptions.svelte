<script lang="ts">
    import { gridSize } from '../store.js'

    //x, y, numBombs
    let gridSizes = {
        "Beginner": [8, 8, 10],
        "Intermediate": [16, 16, 40],
        "Expert": [30, 16, 99]
    }

</script>

<div class="container text-center bg-sky-100 rounded-xl absolute top-1/2 left-1/2 -translate-y-1/2 -translate-x-1/2 max-w-xl">
    <h1 class="font-extrabold text-2xl py-4">Minesweeper 💣</h1>
    <div class="btn-container flex">
        <button on:click={() => gridSize.set(gridSizes["Beginner"])} class="flex flex-col m-auto bg-sky-200 p-3 rounded-xl drop-shadow-xl w-1/4 hover:drop-shadow-sm transition-all duration-300"><span class="m-auto font-bold">Beginner</span> <span class="m-auto">(8x8)</span></button>
        <button on:click={() => gridSize.set(gridSizes["Intermediate"])} class="flex flex-col m-auto bg-sky-200 p-3 rounded-xl drop-shadow-xl w-1/4 hover:drop-shadow-sm transition-all duration-300"><span class="m-auto font-bold">Intermediate</span> <span class="m-auto">(16x16)</span></button>
        <button on:click={() => gridSize.set(gridSizes["Expert"])} class="flex flex-col m-auto bg-sky-200 p-3 rounded-xl drop-shadow-xl w-1/4 hover:drop-shadow-sm transition-all duration-300"><span class="m-auto font-bold">Expert</span> <span class="m-auto">(30x16)</span></button>
    </div>
    <button class="my-4 italic font-thin hover:font-normal">How to play?</button>
</div>


