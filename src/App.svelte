<script lang="ts">
  import Landing from './views/Landing.svelte'
  import AboutUs from './views/AboutUs.svelte'
  import Footer from './views/Footer.svelte'
</script>

<Landing />
<main>
  <div id="container">
    <AboutUs />
  </div>
</main>
<Footer />

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :global(body) {
    background: #fbf8f6;
    font-family: 'Times New Roman', Times, serif;
  }

  :global(::-webkit-scrollbar) {
    width: 0;
  }

  main {
    margin-top: 100vh;
    padding-top: 8.33vw;
    box-sizing: content-box;
  }

  #container {
    width: 90%;
    margin: 0 auto;
  }
</style>
