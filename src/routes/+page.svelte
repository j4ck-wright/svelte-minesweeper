<script lang="ts">
    import { gridSize } from '../store.js';
    import Game from '$lib/Game.svelte';
    import GameOptions from '$lib/GameOptions.svelte';

    let isPlaying = false;
    let GRID_SIZE: number[];

    gridSize.subscribe(value => {
        GRID_SIZE = value;
        isPlaying = GRID_SIZE[0] !== 0 // start game if valid grid size exists
    })

</script>


{#if (!isPlaying)}
    <GameOptions/>
{:else}
    <Game {GRID_SIZE}/>
{/if}


