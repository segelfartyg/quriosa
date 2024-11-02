<script lang="ts">
    import PlusImage from '../assets/noteladplus.svg'
    export let onPostItAdd;
    export let newPostItText: string;
    export let colorHex: string;

</script>

<div>
    <!-- <ColorPicker bind:hex={colorHex} /> -->
    <!-- <input placeholder="component text" type="text" bind:value={newPostItText}> -->
    <button onclick={onPostItAdd}><img aria-label="plusButton" alt="plusButton" src={PlusImage}></button> 

</div>

<style>

    button{
        border: none;
        width:100px;
        margin:auto;
        right:10px;
        bottom:10px;
        position:absolute;
        background:none;
        
   }
</style>