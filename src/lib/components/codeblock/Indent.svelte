<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		indent: number;
		children: Snippet;
	}

	const { indent = 0, children }: Props = $props();
</script>

<br />{@html Array(indent).fill('&#9;').join('')}{@render children()}
