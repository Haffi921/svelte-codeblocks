<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="container mx-auto flex flex-col items-center justify-center">
	{@render children()}
</div>
