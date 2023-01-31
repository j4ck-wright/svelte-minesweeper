<script lang="ts">
	import { gridSize } from "../store";
    import Tile from "./Tile.svelte";

    export let GRID_SIZE: number[]

    let xLength = GRID_SIZE[0];
    let yLength = GRID_SIZE[1];
    let numBombs = GRID_SIZE[2];

    const gameArray = Array(xLength * yLength).fill({}).map((_, i) => ({['index']: i, ['isBomb']: false, ['surroundingBombs']: 0}))
    
    // FIRST TILE OF GAME
    //
    //user clicks tile
    //scatter n bombs in array EXCEPT chosen tile
    //calc. surrounding bombs for all tiles
    //reveal tile

    // REST OF GAME
    // reveal tile
    // check if bomb
    // reveal bombs

</script>

<div class="container text-center bg-sky-100 rounded-xl absolute top-1/2 left-1/2 -translate-y-1/2 -translate-x-1/2 max-w-xl">
    <h1 class="font-extrabold text-2xl pt-4">Minesweeper 💣</h1>
    <h2 class="text-xl">0:00</h2>
    <div class="game-container grid grid-cols-4 p-4" style="grid-template-columns: repeat({xLength}, minmax(0, 1fr))">
        {#each gameArray as t}
            <Tile isBomb={t.isBomb} surroundingBombs={t.surroundingBombs}/>
        {/each}
    </div>
</div>