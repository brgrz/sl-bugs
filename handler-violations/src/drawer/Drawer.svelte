<svelte:options accessors />

<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let label: string;
	export let drawerInstance = undefined;
	export let open = false;

	$: if (open) show();

	const dispatch = createEventDispatcher();

	export const hide = () => {
		drawerInstance.hide();
	};

	export const show = () => {
		drawerInstance.show();
	};
</script>

<sl-drawer
	class="drawer"
	{label}
	bind:this={drawerInstance}
	on:sl-hide|self={() => dispatch('hidden')}
>
	<slot />

	<!-- project own footer slot to sl-drawer's footer slot -->
	<slot name="footer" slot="footer" />
</sl-drawer>

<style>
	sl-drawer::part(body) {
		padding: 0;
	}

	sl-drawer::part(footer) {
		text-align: left;
	}
</style>
