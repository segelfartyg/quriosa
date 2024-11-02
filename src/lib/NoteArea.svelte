<script lang="ts">
    import Draggable from "./Draggable.svelte";
  import type { PostIt } from "./PostIt";
  import PostItComponent from "./PostItComponent.svelte";
    export let postItNotes: PostIt[];
  </script>
<div>
    {#each postItNotes as postIt}
    <Draggable>
     <PostItComponent newText={postIt.text} color={postIt.colorHex}/>
   </Draggable>
   {/each}
</div>

<style>

</style>