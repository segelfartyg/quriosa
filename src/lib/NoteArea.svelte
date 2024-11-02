<script lang="ts">
  import type { PostIt } from "./PostIt";
  import PostItComponent from "./PostItComponent.svelte";
    export let postItNotes: PostIt[];
    let color: string;

  </script>
<div>
    {#each postItNotes as postIt}
     <PostItComponent newText={postIt.text} color={color}/>
     {/each}
</div>

<style>

</style>