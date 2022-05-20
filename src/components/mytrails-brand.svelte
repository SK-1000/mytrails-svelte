<script>
  import {user} from "../stores.js"
</script>


<div class="title p-3 is-flex">
  <i class="fas fa-shoe-prints" style="font-size: 48px; color: rgb(49, 182, 93);" title="Source repo" pos="bottom" uk-tooltip></i>
    {#if $user.email}
      <div class="is-size-7">{$user.email} </div>
    {:else}
      <div class="is-size-7">myTrails-Svelte </div>
    {/if}
  <div class="ml-4">MyTrails</div>
</div>