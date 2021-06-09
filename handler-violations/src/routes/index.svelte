<script lang="ts">
	import { createEventDispatcher, onMount } from 'svelte';

	let name = 'world';
	let option = 'option-2';
	let openButton;
	let closeButton;

	onMount(() => {
		const drawer = document.querySelector('.drawer-overview');

		openButton.addEventListener('click', () => drawer.show());
		closeButton.addEventListener('click', () => drawer.hide());
	});
</script>

<h1>Hello {name}!</h1>

<sl-drawer label="Drawer" class="drawer-overview">
	<sl-tab-group>
		<sl-tab slot="nav" panel="general">General</sl-tab>
		<sl-tab slot="nav" panel="custom">Custom</sl-tab>
		<sl-tab slot="nav" panel="advanced">Advanced</sl-tab>
		<sl-tab slot="nav" panel="disabled" disabled>Disabled</sl-tab>

		<sl-tab-panel name="general">
			<sl-input placeholder="Type something" value={name} />
			<br />
			<sl-select placeholder="Select one" value={option}>
				<sl-menu-item value="option-1">Option 1</sl-menu-item>
				<sl-menu-item value="option-2">Option 2</sl-menu-item>
				<sl-menu-item value="option-3">Option 3</sl-menu-item>
			</sl-select>
		</sl-tab-panel>
		<sl-tab-panel name="custom">This is the custom tab panel.</sl-tab-panel>
		<sl-tab-panel name="advanced">This is the advanced tab panel.</sl-tab-panel>
		<sl-tab-panel name="disabled">This is a disabled tab panel.</sl-tab-panel>
	</sl-tab-group>

	<sl-button slot="footer" type="primary" bind:this={closeButton}>Close</sl-button>
</sl-drawer>

<sl-button bind:this={openButton}>Open Drawer</sl-button>
