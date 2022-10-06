<script>
  import "../styles/app.css";
  import Container from "../components/_shared/Container/Container.svelte";
  import PageTransition from "../components/_shared/PageTransition/PageTransition.svelte";

  export let data;
</script>

<style lang="scss">
  nav {
    background-color: rgb(243 244 246);
    margin-bottom: 3rem;
  }

  a {
    display: inline-block;
    padding: 1rem;
    border-right: solid 2px white;
    transition: all;
    color: black;
    text-decoration: none;

    &:last-child {
      border: none;
    }

    &:hover {
      background-color: rgb(229 231 235);
    }
  }
</style>

<nav class="bg-gray-100 mb-12">
  <Container>
    <a class="" data-sveltekit-prefetch href="/">Home</a>
    <a class="" data-sveltekit-prefetch href="/about">About</a>
  </Container>
</nav>

<PageTransition pathname={data.url}>
  <main>
    <slot />
  </main>
</PageTransition>
