<script lang="ts">
    import ColorPicker from 'svelte-awesome-color-picker';
    import PlusImage from '../assets/noteladplus.svg'
    export let onPostItAdd;
    export let newPostItText: string;
    export let colorHex: string;

</script>

<div>
    <ColorPicker bind:hex={colorHex} />
    <input placeholder="component text" type="text" bind:value={newPostItText}>
    <button onclick={onPostItAdd}><img aria-label="plusButton" alt="plusButton" src={PlusImage}></button>

    <button>ADD FRAME</button>
</div>

<style>
    div {
        width: 100%;
        height: fit-content;
        display: flex;
        flex-direction: row;
        position: absolute;
        bottom: 0;
        height:100px;
        border-top: 1px solid black;
        align-items: center;
        justify-content: center;
    }

    input{
        height:2rem;
        font-family: fantasy;
        border:solid black 1px;
        border-radius: 5px;
        width:300px;
    }

    button{
        border:solid black 1px;
        width:300px;
    }
</style>