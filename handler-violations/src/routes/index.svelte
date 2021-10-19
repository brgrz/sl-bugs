<script>
	import Buttons from './Buttons.svelte';

	let drawer1, btn1;
</script>

<sl-drawer label="Drawer 1" bind:this={drawer1}>
	<h2>Panels</h2>

	<sl-tab-group>
		<sl-tab slot="nav" panel="empty">Empty tab</sl-tab>
		<sl-tab slot="nav" panel="general">General</sl-tab>
		<sl-tab slot="nav" panel="buttons">Buttons</sl-tab>

		<sl-tab-panel name="empty" />
		<sl-tab-panel name="general">
			<Buttons />
		</sl-tab-panel>
		<sl-tab-panel name="buttons">
			<Buttons />
		</sl-tab-panel>
	</sl-tab-group>
</sl-drawer>

<sl-button class="btn-drawer1" on:click={() => drawer1.show()} bind:this={btn1}
	>Open Drawer 1</sl-button
>

<style>
	sl-tab-panel {
		--padding: 1rem;
	}
</style>
