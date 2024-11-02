<script lang="ts">
  import ColorPicker from "svelte-awesome-color-picker";
    export let text: string = ""
    export let color: string = ""
    let colorPickerUp: boolean;
    export let newText: string;

    let inputFieldRef: HTMLTextAreaElement;

    export let left = 0;
	export let top = 0;
	let moving: boolean;
	function onMouseDown(e: MouseEvent) {	
		moving = true;
        console.log("HEJ")
	}
	
	function onMouseMove(e: MouseEvent) {
		if (moving && !colorPickerUp) {
                left += (e.movementX);
                top += (e.movementY);
		}
	}
	
	function onMouseUp() {
		moving = false;
	}

  function onPostItClick(){
    inputFieldRef.focus()
  }
</script>

<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div id="PostItComponent" on:mousedown={onMouseDown} style="--color:{color}; left: {left}px; top: {top}px;" class="draggable">
    <overlay></overlay>
    <header >
        <ColorPicker --input-size="0px" --picker-height="100px"
        --picker-width="100px"
        --slider-width="25px"
        --picker-indicator-size="25px"
        --picker-z-index="10"
        --focus-color="green"label="🎨" 
        bind:isOpen={colorPickerUp}
        bind:hex={color}
        ></ColorPicker>
    </header>
    {text}
  
    <div id="postItContent">
        <textarea bind:this={inputFieldRef}  bind:value={newText}> </textarea>    
    </div>

    
</div>
<svelte:window on:mouseup={onMouseUp} on:mousemove={onMouseMove} />
<style>
   
        #PostItComponent {
        border: solid black 2px;
        border-radius: 5px;
        height:200px;
        width:200px;
        background: var(--color);
        display:flex;
        flex-direction: column;
        position: absolute;
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


    .draggable {
		user-select: none;
		cursor: move;
		position: absolute;
	}
</style>
