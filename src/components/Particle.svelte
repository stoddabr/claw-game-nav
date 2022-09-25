<script lang="ts" context="module">
	const material = new MeshStandardMaterial({ color: 'green', wireframe: false });
	export const muted = writable(true);
</script>

<script lang="ts">
	import { Mesh, type Position, type Rotation } from '@threlte/core';
	import { Collider, RigidBody } from '@threlte/rapier';
	import { writable } from 'svelte/store';
	import { BoxGeometry, MeshStandardMaterial } from 'three';

	export let position: Position | undefined = undefined;
	export let rotation: Rotation | undefined = undefined;

	export let height: number;
	export let width: number;
	export let depth: number;

	const geometry = new BoxGeometry(height, width, depth);
</script>

<RigidBody type={'dynamic'} {position} {rotation}>
	<Collider
		contactForceEventThreshold={30}
		restitution={0.4}
		shape={'cuboid'}
		args={[height / 2, width / 2, depth / 2]}
	/>
	<Mesh castShadow receiveShadow geometry={geometry.scale(height, width, depth)} {material} />
</RigidBody>
