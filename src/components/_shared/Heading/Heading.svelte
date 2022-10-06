<script lang="ts">
  export let component: string = "h1";
  export let classes: string = "";
</script>

<style>
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-weight: 700;
    margin: 0;
  }

  h1,
  .h1 {
    font-size: 3rem; /* 48px */
    line-height: 1;
  }
  h2 {
    font-size: 2.25rem; /* 36px */
    line-height: 2.5rem; /* 40px */
  }
  h3 {
    font-size: 1.875rem; /* 30px */
    line-height: 2.25rem; /* 36px */
  }
  h4 {
    font-size: 1.5rem; /* 24px */
    line-height: 2rem; /* 32px */
  }
  h5 {
    font-size: 1.25rem; /* 20px */
    line-height: 1.75rem; /* 28px */
  }
  h6 {
    font-size: 1.125rem; /* 18px */
    line-height: 1.75rem; /* 28px */
  }
</style>

{#if component === "h1"}
  <h1 class="h1">
    <slot />
  </h1>
{:else if component === "h2"}
  <h2 class={classes} {...$$props}>
    <slot />
  </h2>
{:else if component === "h3"}
  <h3 class={classes} {...$$props}>
    <slot />
  </h3>
{:else if component === "h4"}
  <h4 class={classes} {...$$props}>
    <slot />
  </h4>
{:else if component === "h5"}
  <h5 class={classes} {...$$props}>
    <slot />
  </h5>
{:else if component === "h6"}
  <h6 class={classes} {...$$props}>
    <slot />
  </h6>
{/if}
