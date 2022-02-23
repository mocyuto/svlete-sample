<script lang="ts">
	import { createEventDispatcher } from "svelte";
	import { name } from "./store";

	const dispatch = createEventDispatcher();

	let text: string;
	name.subscribe((value) => {
		text = value;
	});

	function update() {
		dispatch("message", {
			text: text,
		});
	}
</script>

<button on:click={update}> update! </button>
