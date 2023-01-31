<script type="ts">
    export let index;
    export let isBomb;
    export let surroundingBombs;
    export let hidden;
</script>

<div class="aspect-square bg-sky-400 z-10">
   <div class="h-full cursor-pointer">
    <p class="relative top-1/2 -translate-y-1/2 opacity-0">{surroundingBombs}</p>
   </div>
</div>