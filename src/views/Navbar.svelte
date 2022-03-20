<script lang="ts">
  export let onAboutUs: () => void
  export let onPricing: () => void
</script>

<nav>
  <a href="#AboutUs" on:click={() => onAboutUs()}>À Propos</a>
  <a href="#Pricing" on:click={() => onPricing()}>Nos Tarifs</a>
  <a href="#Footer">Nous Joindre</a>
</nav>

<style>
  nav {
    position: absolute;
    width: 60%;
    display: flex;
    justify-content: space-around;
    z-index: 10;
    top: 1.5vw;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
  }

  a {
    font-size: 1vw;
    color: #fbf8f6;
    position: relative;
    text-decoration: none;
    padding-bottom: 8px;
  }
  a:before,
  a:after {
    content: '';
    position: absolute;
    bottom: 2px;
    left: 0;
    right: 0;
    height: 2px;
    background-color: #fbf8f6;
  }
  a:before {
    opacity: 0;
    transform: translateY(-8px);
    transition: transform 0s cubic-bezier(0.175, 0.885, 0.32, 1.275), opacity 0s;
  }
  a:after {
    opacity: 0;
    transform: translateY(4px);
    transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275),
      opacity 0.2s;
  }
  a:hover:before,
  a:hover:after,
  a:focus:before,
  a:focus:after {
    opacity: 1;
    transform: translateY(0);
  }
  a:hover:before,
  a:focus:before {
    transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275),
      opacity 0.2s;
  }
  a:hover:after,
  a:focus:after {
    transition: transform 0s 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275),
      opacity 0s 0.2s;
  }
</style>
