<script lang="ts">
	import { HTML } from '@threlte/extras';
	import { Canvas } from '@threlte/core';
	import { World } from '@threlte/rapier';
	import ChainScene from '../scenes/FallingBoxes.svelte';
</script>

<div class="background">
	<div class="canvas-container">
		<Canvas>
			<World>
				<ChainScene />

				<HTML slot="fallback" transform>
					<p class="text-xs">
						It seems your browser<br />
						doesn't support WASM.<br />
						I'm sorry.
					</p>
				</HTML>
			</World>
		</Canvas>
	</div>
</div>

<style>
	.background {
		height: 100%;
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.canvas-container {
		height: 80vh;
		width: 80vw;
	}
</style>
