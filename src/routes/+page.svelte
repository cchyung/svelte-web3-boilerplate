<script lang="ts">
  import { getAccount, watchAccount, type GetAccountResult } from "@wagmi/core";
  import { onMount } from "svelte";

  let account: GetAccountResult;
  onMount(() => {
    watchAccount(() => {
      account = getAccount();
    });
  });
</script>

{#if account}
  <w3m-core-button />
  <p>{account.address}</p>
{/if}
