<script>
	let drawer2;
	let items = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
	let selected;

	const edit = (item) => {
		selected = item;
		drawer2.show();
	};
</script>

<div class="buttons">
	{#each items as item}
		<div class="button">
			<div class="icon">
				<svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"
					><title>Fish</title><path
						d="M512 256c0-16.54-14.27-46.76-45.61-74a207.06 207.06 0 00-60.28-36.12 3.15 3.15 0 00-3.93 1.56c-.15.29-.3.57-.47.86l-9.59 15.9a183.24 183.24 0 00.07 183.78l.23.39 8.74 16a4 4 0 004.94 1.82C479.63 337.42 512 281.49 512 256zm-93.92-.14a16 16 0 1113.79-13.79 16 16 0 01-13.79 13.79z"
					/><path
						d="M335.45 256a214.8 214.8 0 0129.08-108l.12-.21 4.62-7.67a4 4 0 00-2.59-6 284.29 284.29 0 00-39.26-5.39 7.94 7.94 0 01-4.29-1.6c-19.28-14.66-57.5-40.3-96.46-46.89a16 16 0 00-18 20.18l10.62 37.17a4 4 0 01-2.42 4.84c-36.85 13.69-68.59 38.75-91.74 57.85a8 8 0 01-10.06.06q-4.72-3.75-9.69-7.39c-39.64-28.95-86.21-32.76-88.17-32.9a16 16 0 00-16.83 19.4c.42 1.93 9.19 40.69 31.7 71.61a8.09 8.09 0 010 9.55C9.57 291.52.8 330.29.38 332.22a16 16 0 0016.83 19.4c2-.14 48.53-4 88.12-32.88q4.85-3.56 9.47-7.22a8 8 0 0110.06.07c23.25 19.19 55.05 44.28 92 58a4 4 0 012.42 4.83l-10.66 37.18a16 16 0 0018 20.18c17.16-2.9 51.88-12.86 96.05-46.83a8.15 8.15 0 014.36-1.65 287.36 287.36 0 0039.22-5.3 4 4 0 002.69-5.83l-4.51-8.29A214.81 214.81 0 01335.45 256z"
					/></svg
				>
			</div>

			<div class="title">
				<span class="name">click here {item}</span>
				<br />
				<small class="subtitle">
					{#if item}
						<span>click here {item}</span>
					{/if}
				</small>
			</div>

			<div class="edit">
				<sl-button type="default" size="medium" circle on:click={() => edit(item)}
					><sl-icon name="pencil-square" /></sl-button
				>
			</div>

			<sl-button on:click={() => console.log(item)}>{item}</sl-button>
			<sl-button type="default" size="medium" circle on:click={() => edit(item)}>
				<sl-icon name="pencil-square" /></sl-button
			>
		</div>
	{/each}
</div>

<sl-drawer label="Drawer 2" bind:this={drawer2}>
	<div class="drawer-content">
		{#if selected}
			<div class="drawer-header">
				<h2>
					{selected}
				</h2>
			</div>

			<div class="drawer-body">
				<sl-form class="form-overview">
					<sl-input name="name" type="text" label="Name" />
					<br />
					<sl-select name="favorite" label="Select your favorite">
						<sl-menu-item value="birds">Birds</sl-menu-item>
						<sl-menu-item value="cats">Cats</sl-menu-item>
						<sl-menu-item value="dogs">Dogs</sl-menu-item>
					</sl-select>
					<br />
					<sl-checkbox name="agree" value="yes"> I totally agree </sl-checkbox>
					<br /><br />
					<sl-button submit>Submit</sl-button>
				</sl-form>
			</div>
		{/if}
	</div>
</sl-drawer>

<style>
	.buttons {
		display: grid;
		grid-auto-flow: row;
		grid-gap: 1rem;
	}

	.button {
		display: flex;
		justify-content: space-between;
	}
</style>
