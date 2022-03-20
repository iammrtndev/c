<script>
  import mapboxgl from 'mapbox-gl/dist/mapbox-gl.js'
  import { onMount } from 'svelte'
  mapboxgl.accessToken =
    'pk.eyJ1IjoiaWFtbXJ0bmRldiIsImEiOiJja3g3NXg5eHMwZ2h6MnZvMGJ4YmI1YWh3In0.f7XXNZlmCi7EYSoFnMSIAA'

  export let id = 'mapbox'

  onMount(() => {
    new mapboxgl.Map({
      container: id,
      style: 'mapbox://styles/mapbox/streets-v11',
      center: [2.2944813, 48.8583701],
      zoom: 15
    })
  })
</script>

<div {id} />

<style>
  div {
    width: 100%;
    height: 100%;
  }

  :global(.mapboxgl-ctrl-bottom-left, .mapboxgl-ctrl-bottom-right) {
    display: none;
  }
</style>
