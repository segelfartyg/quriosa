<script lang="ts">
  import ColorPicker from "svelte-awesome-color-picker";

    export let text: string = ""
    export let color: string = ""
    export let newText: string;
    let inputFieldRef: HTMLTextAreaElement;


  function onPostItClick(){
    inputFieldRef.focus()
  }
</script>

<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div id="PostItComponent" style='--color:{color}' on:click={onPostItClick}>
    <overlay></overlay>
    <header>
        <ColorPicker --input-size="0px" label="🎨" bind:hex={color}></ColorPicker>
    </header>
    {text}
    <div id="postItContent">
        <textarea bind:this={inputFieldRef}  bind:value={newText}> </textarea>    
    </div>
    
    
</div>

<style>
   
        #PostItComponent {
        border: solid black 2px;
        border-radius: 5px;
        height:200px;
        width:200px;
        background: var(--color);
        display:flex;
        flex-direction: column;
    }

    #postItContent{
        height:100%;
        width:100%;
        display:flex;
    }

    header{
        height:50px;
        border-bottom: 2px solid black;
        background: var(--color);
    }

    overlay {
        position:absolute;
        height:100%;
        width: 100%;
        background: linear-gradient(160deg,rgba(255, 255, 255, 0) 0%, rgba(156, 156, 156, 0.116) 50%, rgba(0, 0, 0, 0.486) 100%);
        top:0;
    }

    textarea{
        z-index: 5;
        background:none;
        width: 90%;
        padding:0;
        border:none;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        height:90%;
        top:0;
        margin:auto;
    }

    textarea:focus{
        border: none;
        outline:none;
    }
</style>