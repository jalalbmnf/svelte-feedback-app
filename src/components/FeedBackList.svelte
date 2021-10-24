<script>
  import { fade, scale } from "svelte/transition";

  import FeedBackItem from "./FeedBackItem.svelte";

  import { FeedBackStore } from "../stores";
</script>

{#each $FeedBackStore as fb (fb.id)}
  <div in:scale out:fade={{ duration: 500 }}>
    <FeedBackItem {fb} />
  </div>
{/each}
