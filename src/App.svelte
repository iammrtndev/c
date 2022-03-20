<script lang="ts">
  import Landing from './views/Landing.svelte'
  import AboutUs from './views/AboutUs.svelte'
  import Footer from './views/Footer.svelte'
  import Pricing from './views/Pricing.svelte'
  import Navbar from './views/Navbar.svelte'
  import { onMount } from 'svelte'

  const style: { [k: string]: string } = {}
  let show = 'AboutUs'
  onMount(() => {
    if (document.location.hash == 'Pricing') show = 'Pricing'
  })

  window.visualViewport.addEventListener('resize', () => {
    if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent)) return

    style.main = window.devicePixelRatio == 1 ? '' : 'overflow: auto'
    style.container = `transform: scale(${window.devicePixelRatio})`
  })
</script>

<Navbar
  onAboutUs={() => {
    show = 'AboutUs'
  }}
  onPricing={() => {
    show = 'Pricing'
  }}
/>
<Landing />
<main style={style.main}>
  <div id="container" style={style.container}>
    {#if show == 'AboutUs'}
      <AboutUs />
    {/if}
    {#if show == 'Pricing'}
      <Pricing />
    {/if}
  </div>
</main>
<Footer />

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :global(html) {
    scroll-behavior: smooth;
    height: fill-available;
    height: -webkit-fill-available;
  }

  :global(body) {
    font-family: 'Times New Roman', Times, serif;
  }

  :global(body::-webkit-scrollbar) {
    width: 0;
  }

  main {
    z-index: -10;
    margin-top: 100vh;
    padding-top: 8.33vw;
    box-sizing: content-box;
    background: #fbf8f6;
  }

  #container {
    width: 90%;
    margin: 0 auto;
  }
</style>
