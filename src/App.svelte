<script lang="ts">
  import AnimationArea from './lib/AnimationArea.svelte'
  import OptionsArea from './lib/OptionsArea.svelte';
  let animationComponents: string[] = []
  let newComponentText: string;
  function onComponentAddHandler(){
    animationComponents.push(newComponentText);
    animationComponents = [...animationComponents];
  }

</script>

<main>
    <AnimationArea bind:animationComponents={animationComponents}/>
    <OptionsArea onComponentAdd={onComponentAddHandler} bind:newComponentText={newComponentText}/>
</main>

<style>

</style>
