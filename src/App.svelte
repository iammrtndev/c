<script lang="ts">
  import Landing from './views/Landing.svelte'
  import AboutUs from './views/AboutUs.svelte'
  import Footer from './views/Footer.svelte'

  let containerStyle: string
  let mainStyle: string

  if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent) == false) {
    window.visualViewport.addEventListener('resize', () => {
      mainStyle = window.devicePixelRatio == 1 ? '' : 'overflow: auto'
      containerStyle = `transform: scale(${window.devicePixelRatio})`
    })
  }
</script>

<Landing />
<main style={mainStyle}>
  <div id="container" style={containerStyle}>
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

  :global(html) {
    scroll-behavior: smooth;
    height: fill-available;
    height: -webkit-fill-available;
  }

  :global(body) {
    background: #fbf8f6;
    font-family: 'Times New Roman', Times, serif;
    scroll-snap-type: y mandatory;
  }

  :global(body::-webkit-scrollbar) {
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
