<script>
  import { FeedBackStore } from "../stores";

  $: count = $FeedBackStore.length;
  $: average =
    $FeedBackStore.reduce((a, { rating }) => a + rating, 0) /
    $FeedBackStore.length;
</script>

<div class="feedback-stats">
  {#if count !== 0}
    <h4>{count} reviews</h4>
  {:else}
    <p />
  {/if}

  {#if !average.toString().includes("NaN")}
    <h4>Rating average {average.toFixed()}</h4>
  {:else}
    <p />
  {/if}
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
