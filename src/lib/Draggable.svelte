<script lang="ts">
	export let left = 0;
	export let top = 0;
	
	let moving = false;
	
	function onMouseDown() {
		moving = true;
	}
	
	function onMouseMove(e: MouseEvent) {
		if (moving) {
                left += (e.movementX);
                top += (e.movementY);
		}
	}
	
	function onMouseUp() {
		moving = false;
	}
	
</script>

<style>
	.draggable {
		user-select: none;
		cursor: move;
		position: absolute;
	}

</style>

<section aria-hidden="true" on:mousedown={onMouseDown} style="left: {left}px; top: {top}px;" class="draggable">
	<slot></slot>
</section>

<svelte:window on:mouseup={onMouseUp} on:mousemove={onMouseMove} />