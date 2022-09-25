<script lang="ts">
	import {
		AudioListener,
		DirectionalLight,
		Object3DInstance,
		OrbitControls,
		PerspectiveCamera,
		useFrame
	} from '@threlte/core';
	import { Debug } from '@threlte/rapier';
	import { GridHelper } from 'three';
	import Emitter from '../components/Emitter.svelte';
	import Ground from '../components/Ground.svelte';

	let camerazPosition = 0;
	useFrame((ctx, delta) => {
		const zPerSec = 20;
		camerazPosition += zPerSec * delta;
	});
</script>

<PerspectiveCamera position={{ y: 20, z: 20, x: 20 }}>
	<OrbitControls enableZoom={false} />
	<AudioListener />
</PerspectiveCamera>

<DirectionalLight shadow position={{ y: 20, x: 8, z: -3 }} />

<Object3DInstance object={new GridHelper(50)} />

<Ground />

<Emitter />
