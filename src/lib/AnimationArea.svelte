<script lang="ts">
  import Component from "./Component.svelte";
  import Draggable from "./Draggable.svelte";
  export let animationComponents: string[];
</script>

<div>
  {#each animationComponents as component}
   <Draggable>
    <Component letter={component} />
  </Draggable>
  {/each}
</div>

<style>
  div {
    height:500px;
    width:500px;
    border:solid black 3px;
    border-radius: 10px;
    position: relative;
  }
</style>
