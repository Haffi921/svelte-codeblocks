<script lang="ts">
	import * as Codeblock from './codeblock';

	class MouseEventView {
		// Modulating Keys
		shiftKey = $state(false);
		altKey = $state(false);
		ctrlKey = $state(false);

		// Mouse Button
		button = $state(0);
		buttons = $state(0);

		// Coordinates
		client = $state({ x: 0, y: 0 });
		page = $state({ x: 0, y: 0 });
		screen = $state({ x: 0, y: 0 });
		movement = $state({ x: 0, y: 0 });
		offset = $state({ x: 0, y: 0 });
		test = $state([2, 3, 'test data']);

		update(event: MouseEvent) {
			// Modulating Keys
			this.shiftKey = event.shiftKey;
			this.altKey = event.altKey;
			this.ctrlKey = event.ctrlKey;

			// Mouse Button
			this.button = event.button;
			this.buttons = event.buttons;

			// Coordinates
			this.client = { x: event.clientX, y: event.clientY };
			this.page = { x: event.pageX, y: event.pageY };
			this.screen = { x: event.screenX, y: event.screenY };
			this.movement = { x: event.movementX, y: event.movementY };
			this.offset = { x: event.offsetX, y: event.offsetY };
		}
	}

	const mouseEventView = new MouseEventView();

	$effect(() => {
		const update = mouseEventView.update.bind(mouseEventView);
		addEventListener('mousemove', update);
		return () => {
			removeEventListener('mousemove', update);
		};
	});
</script>

<Codeblock.Root>
	<Codeblock.Class.Root name="MouseEvent">
		<Codeblock.Indent indent={1}>
			<Codeblock.Comment value="Modulating Keys" />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="shiftKey" value={mouseEventView.shiftKey} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="altKey" value={mouseEventView.altKey} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="ctrlKey" value={mouseEventView.ctrlKey} />
		</Codeblock.Indent>
		<br />

		<Codeblock.Indent indent={1}>
			<Codeblock.Comment value="Mouse Button" />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="button" value={mouseEventView.button} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="buttons" value={mouseEventView.buttons} />
		</Codeblock.Indent>
		<br />

		<Codeblock.Indent indent={1}>
			<Codeblock.Comment value="Coordinates" />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="client" value={mouseEventView.client} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="page" value={mouseEventView.page} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="screen" value={mouseEventView.screen} />
		</Codeblock.Indent>
		<Codeblock.Indent indent={1}>
			<Codeblock.Class.Property name="test" value={mouseEventView.test} />
		</Codeblock.Indent>
	</Codeblock.Class.Root>
</Codeblock.Root>
