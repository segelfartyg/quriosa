<script lang="ts">
    export let onComponentAdd;
    export let newComponentText: string;
</script>

<div>
    <input placeholder="frame" type="number">
    <input placeholder="component text" type="text" bind:value={newComponentText}>

    <button onclick={onComponentAdd}>ADD COMPONENT</button>
    <button>ADD FRAME</button>
</div>

<style>
    div {
        margin:auto;
        width: 300px;
        height: fit-content;
        padding-top: 1rem;
        padding-bottom: 1rem;
        border:solid black 3px;
        border-radius: 10px;
        margin-top:1rem;
        display: flex;
        flex-direction: column;
        padding:1rem;
        align-items: center;
        gap: 15px;
        
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