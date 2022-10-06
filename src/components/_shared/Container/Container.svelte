<style lang="scss">
  .container {
    margin: auto;
    max-width: 2560px;
    padding: 0 1rem;
    transition: all 1s;

    @include breakpoint(sm) {
      padding: 0 2rem;
    }
  }
</style>

<div class="container">
  <slot />
</div>
