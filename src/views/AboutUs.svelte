<script lang="ts">
  import PrettyCard from 'src/components/PrettyCard.svelte'
  import oneJPG from 'src/assets/1.jpg'
  import twoJPG from 'src/assets/2.jpg'
  import threeJPG from 'src/assets/3.jpg'
  import { onMount } from 'svelte'
  import Rellax from 'rellax'
  import IntersectionObserver from 'svelte-intersection-observer'

  let one, two, three
  const rellax: any = {}

  onMount(() => {
    if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent)) {
      one = two = three = null
      return
    }

    rellax.oneImg = new Rellax('#one img', {
      speed: -1,
      center: true,
    })
    rellax.oneText = new Rellax('#one .text', {
      speed: -2,
      center: true,
    })
    rellax.twoH2 = new Rellax('#two h2', {
      speed: -1,
      center: true,
    })
    rellax.twoText = new Rellax('#two .text', {
      speed: -2,
      center: true,
    })
    rellax.threeH2 = new Rellax('#three h2', {
      speed: -1,
      center: true,
    })
    rellax.threeText = new Rellax('#three .text', {
      speed: 2,
      center: true,
    })
  })
</script>

<div id="AboutUs">
  <PrettyCard>
    <h1 slot="title">Pourquoi le <u class="C">C</u> ?</h1>

    <section>
      <article id="one" bind:this={one}>
        <IntersectionObserver
          element={one}
          on:intersect={() => {
            rellax.oneImg.refresh()
            rellax.oneText.refresh()
          }}
        >
          <img src={oneJPG} alt="" />
          <div class="text">
            <h2>
              <span class="C">C</span>
              <span>L</span>
              <span>A</span>
              <span>S</span>
              <span>S</span>
              <span>E</span>
            </h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec
              porttitor felis blandit viverra varius.
              <br />
              <br />
              Vestibulum a dignissim metus. In eleifend tellus enim, sit amet venenatis
              libero lobortis sed. Nunc ullamcorper ligula eu sagittis lobortis.
              Cras ornare ante sit amet placerat euismod.
            </p>
          </div>
        </IntersectionObserver>
      </article>

      <article id="two" bind:this={two}>
        <IntersectionObserver
          element={two}
          on:intersect={() => {
            rellax.twoH2.refresh()
            rellax.twoText.refresh()
          }}
        >
          <h2>
            <span class="C">C</span>onnaissance &<br />
            <span class="white">Expertise</span>
          </h2>
          <img src={twoJPG} alt="" />
          <div class="text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec
            porttitor felis blandit viverra varius. Vestibulum a dignissim
            metus.
          </div>
        </IntersectionObserver>
      </article>

      <article id="three">
        <IntersectionObserver
          element={three}
          on:intersect={() => {
            rellax.threeH2.refresh()
            rellax.threeText.refresh()
          }}
        >
          <h2>
            <span class="C">C</span>onfortable<br />
            <span class="C">C</span>onsidérable<br />
            <span class="C">C</span>onvenable<br />
            <span class="C">C</span>...
          </h2>
          <img src={threeJPG} alt="" />
          <div class="text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec
            porttitor felis blandit viverra varius. Vestibulum a dignissim
            metus.
          </div>
        </IntersectionObserver>
      </article>
    </section>
  </PrettyCard>
</div>

<style>
  .C {
    font-weight: bold;
  }

  .white {
    color: #fbf8f6;
  }

  h1 {
    font-weight: normal;
    font-size: 6vw;
    color: #290001;
  }

  article {
    position: relative;
  }

  article + article {
    margin-top: 15vw;
  }

  img {
    z-index: 1;
    outline: 0.41vw solid #fbf8f6;
  }

  h2 {
    font-size: 6.66vw;
    font-weight: normal;
  }

  .text {
    z-index: -1;
    background: #4f4f54;
    color: #fbf8f6;
    font-size: 1.66vw;
    line-height: 150%;
  }

  #one {
    height: 54.16vw;
  }

  #one img {
    width: 37.5vw;
  }

  #one h2 {
    position: absolute;
    left: 4.16vw;
    top: 50%;
    width: 12.5vw;
    height: 100%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }

  #one .text {
    position: absolute;
    z-index: -1;
    top: 4.16vw;
    left: 33.33vw;
    width: 41.66vw;
    height: 45.83vw;
    padding: 8.33vw 4.16vw 8.33vw 16.66vw;
  }

  #two {
    height: 45.83vw;
  }

  #two h2 {
    width: 62.5vw;
    text-align: center;
    line-height: 100%;
  }

  #two img {
    position: absolute;
    top: 16.66vw;
    right: 0;
    width: 45.83vw;
  }

  #two .text {
    position: absolute;
    top: 6.25vw;
    width: 60.41vw;
    height: 31.25vw;
    padding: 10.41vw 35.41vw 4.16vw 4.16vw;
  }

  #three {
    height: 54.16vw;
  }

  #three img {
    position: absolute;
    top: 8.33vw;
    left: 50%;
    transform: translateX(-50%);
    width: 33.33vw;
  }

  #three .text {
    position: absolute;
    right: 0;
    bottom: 0;
    width: 37.5vw;
    height: 33.33vw;
    padding: 4.16vw 4.16vw 4.16vw 20.83vw;
  }
</style>
