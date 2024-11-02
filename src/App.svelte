<script lang="ts">
  import NoteArea from './lib/NoteArea.svelte';
  import OptionsArea from './lib/OptionsArea.svelte';
  import type { PostIt } from './lib/PostIt';
  let postItNotes: PostIt[] = []
  let newPostItText: string;
  let colorHex: string
  function onPostItAddHandler(){
  
   let newPostIt: PostIt = {
      text: newPostItText,
      colorHex: colorHex
    }
    postItNotes.push(newPostIt);
    postItNotes = [...postItNotes];
  }

</script>

<main>
    <NoteArea bind:postItNotes={postItNotes}/>
    <OptionsArea onPostItAdd={onPostItAddHandler} bind:newPostItText={newPostItText} bind:colorHex={colorHex}/>     
</main>

<style>
  main {
    width:100%;
  }
</style>
