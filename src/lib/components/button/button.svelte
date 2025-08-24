<svelte:options customElement={{ tag: 'my-button' }} />

<script lang="ts">
  export let variant = 'default'
  export const disabled:boolean = false
</script>

<button class="button {variant}" disabled={disabled} on:click={() => console.log('click')}>
  <slot />
</button>

<style>
  .button {
    font-size: var(--font-size-3);
    font-weight: var(--font-weight-medium);
    padding-inline: var(--size-8);
    padding-block: var(--size-3);
    border-radius: var(--radius-2);
    box-shadow: var(--shadow-2);
  }
  .button.default {
    background: var(--white);
    color: var(--indigo-8);

    &:hover {
      background-color: var(--gray-3);
    }
  }

  .button.primary {
    background-color: var(--primary);
    color: var(--white);

    &:hover {
      background-color: var(--primary-accent);
    }
  }
</style>