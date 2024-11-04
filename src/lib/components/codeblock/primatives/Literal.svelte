<script lang="ts">
	interface Props {
		value: unknown;
	}

	const { value }: Props = $props();
</script>

<span style="color: var(--shiki-constant)">{value}</span>
