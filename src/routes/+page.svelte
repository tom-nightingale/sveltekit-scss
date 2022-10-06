<script lang="ts">
  import type { PageData } from "./$types";
  import Container from "../components/_shared/Container/Container.svelte";
  import Heading from "../components/_shared/Heading/Heading.svelte";

  /** @type {import('./$types').PageData} */
  export let data: PageData;
  let launches = data.result.data.launchesPast;
</script>

<style lang="scss">
  p {
    margin-top: 0;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

  .container {
    background-color: rgb(15 23 42);
    padding-top: 2.5rem;
    margin-top: 2.5rem;
  }

  .heading {
    color: white;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 2rem;
    padding: 2rem 0;
    margin-top: 0;

    @include breakpoint(sm) {
      grid-gap: 3rem;
    }
  }

  .card {
    margin-bottom: 1rem;
    background: white;
    border-radius: 0.375rem; /* 6px */
    padding: 1rem;
  }

  strong {
    display: block;
  }
</style>

<Container>
  <Heading component="h1">Welcome to sveltekit</Heading>
  <p>
    Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
  </p>
</Container>

<div class="container">
  <Container>
    <div class="heading">
      <Heading component="h2">SpaceX launches</Heading>
    </div>
    {#if data}
      <ul class="grid">
        {#each launches as mission}
          <li class="card">
            <strong>{mission.mission_name}</strong>
            {mission.launch_site.site_name_long}
          </li>
        {/each}
      </ul>
    {/if}
  </Container>
</div>
