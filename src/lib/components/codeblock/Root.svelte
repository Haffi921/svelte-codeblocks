<script lang="ts">
	import type { Snippet } from 'svelte';

	const dark = $state(true);

	interface Props {
		children: Snippet;
	}

	const { children }: Props = $props();
</script>

<pre
	class="shiki shiki-themes github-light github-dark"
	class:dark
	oncontextmenu={(e) => e.preventDefault()}><code
		><span class="line"
			>{@render children()}
<span class="line"></span></span
		></code
	></pre>
