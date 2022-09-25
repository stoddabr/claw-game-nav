<script lang="ts">
	import { Color } from 'three';
	import { HTML } from '@threlte/extras';
	import { Canvas } from '@threlte/core';
	import { World, Debug } from '@threlte/rapier';
	import FallingBoxes from '../../scenes/FallingBoxes.svelte';
</script>

<Canvas>
	<World>
		{#if true}
			<Debug color={new Color('#fff').convertSRGBToLinear()} />
		{/if}
		<FallingBoxes />

		<HTML slot="fallback" transform>
			<p class="text-xs">
				It seems your browser<br />
				doesn't support WASM.<br />
				I'm sorry.
			</p>
		</HTML>
	</World>
</Canvas>
