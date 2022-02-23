<script lang="ts">
  import { name } from "./store";
  let text: string;
  name.subscribe((value) => {
    text = value;
  });
  $: name.set(text);
</script>

<input bind:value={text} />
