<script>
	import Form from './Form.svelte';
	import Buttons from './Buttons.svelte';

	import Drawer from '../drawer/Drawer.svelte';
	import DrawerBody from '../drawer/DrawerBody.svelte';
	import DrawerHeader from '../drawer/DrawerHeader.svelte';
	import DrawerContent from '../drawer/DrawerContent.svelte';

	let drawer1, btn1;
</script>

<Drawer label="Drawer 1" bind:this={drawer1}>
	<DrawerBody>
		<DrawerContent>
			<DrawerHeader>
				<h2>Panels</h2>
			</DrawerHeader>

			<sl-tab-group>
				<sl-tab slot="nav" panel="empty">Empty tab</sl-tab>
				<sl-tab slot="nav" panel="general">General</sl-tab>
				<sl-tab slot="nav" panel="advanced">Advanced</sl-tab>

				<sl-tab-panel name="empty" />
				<sl-tab-panel name="general">
					<Buttons />
				</sl-tab-panel>
				<sl-tab-panel name="advanced">
					<Form />
				</sl-tab-panel>
			</sl-tab-group>
		</DrawerContent>
	</DrawerBody>
</Drawer>

<sl-button class="btn-drawer1" on:click={() => drawer1.show()} bind:this={btn1}
	>Open Drawer 1</sl-button
>

<style>
	sl-tab-panel {
		--padding: 1rem;
	}
</style>
