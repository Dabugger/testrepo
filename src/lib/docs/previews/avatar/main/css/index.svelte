<script lang="ts">
	import { createAvatar, melt } from '$lib/index.js';

	const {
		elements: { image, fallback },
	} = createAvatar({
		src: 'https://avatars.githubusercontent.com/u/1162160?v=4',
	});

	// With an exaggerated fallback delay
	const {
		elements: { image: imageA, fallback: fallbackA },
	} = createAvatar({
		src: 'https://avatars.githubusercontent.com/u/5968653?v=4',
		delayMs: 650,
	});

	// A blank source to demonstrate the fallback
	const {
		elements: { image: imageB, fallback: fallbackB },
	} = createAvatar({
		src: '',
	});
</script>

<div class="root">
	<div class="item">
		<img use:melt={$image} alt="Avatar" class="avatar" />
		<span use:melt={$fallback} class="fallback">RH</span>
	</div>

	<div class="item">
		<img use:melt={$imageA} alt="Avatar" class="avatar" />
		<span use:melt={$fallbackA} class="fallback">SH</span>
	</div>

	<div class="item">
		<img use:melt={$imageB} alt="Avatar" class="avatar" />
		<span use:melt={$fallbackB} class="fallback">UI</span>
	</div>
</div>

<style>
	.root {
		display: flex;
		width: 100%;
		align-items: center;
		justify-content: center;
		gap: 1.5rem;
	}

	.item {
		display: flex;
		height: 4rem;
		width: 4rem;
		align-items: center;
		justify-content: center;
		border-radius: 9999px;
		background-color: rgb(var(--color-neutral-100) / 1);
	}

	.item > .avatar {
		height: 100%;
		width: 100%;
		border-radius: inherit;
	}

	.item > .fallback {
		font-size: 1.875rem;
		line-height: 1.875rem;
		font-weight: 500;
		color: rgb(var(--color-magnum-700) / 1);
	}
</style>
