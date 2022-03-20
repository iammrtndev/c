<script>
  import landing from 'src/assets/landing.mp4'
  import scissorLeft from 'src/assets/scissorLeft.png'
  import scissorRight from 'src/assets/scissorRight.png'
  import { waitFor } from 'src/utils'

  let cut = false
  const scroll = window.innerHeight * 0.6
</script>

<div id="landing">
  <div id="cover" />
  <video autoplay loop muted playsinline src={landing} />
  <div id="line" />
</div>

<div
  id="scroll"
  on:pointerenter={async () => {
    cut = true
    if (window.scrollY < scroll)
      window.scrollTo({ top: scroll, behavior: 'smooth' })
    await waitFor(300)
    cut = false
  }}
>
  <div id="scissors" class:cut>
    <img class="scissor left" src={scissorLeft} alt="" />
    <img class="scissor right" src={scissorRight} alt="" />
  </div>
  <div id="bg" />
</div>

<style>
  #landing {
    position: absolute;
    z-index: -1;
    top: 0;
    width: 100%;
    min-height: 100vh;
    min-height: fill-available;
    min-height: -webkit-fill-available;
  }

  #landing video {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  #cover {
    position: absolute;
    z-index: 1;
    width: 100%;
    height: 100%;
    background-image: url('src/assets/landing.png');
    background-position: center;
    background-size: cover;
  }

  #line {
    position: absolute;
    z-index: 2;
    width: 100%;
    bottom: 0;
    height: 0.41vw;
    background: #4f4f54;
  }

  #scissors {
    position: relative;
    z-index: 1;
  }

  .scissor {
    height: 3.125vw;
    position: absolute;
    left: 50%;
    transition: all 100ms ease-in-out;
  }
  .scissor.left {
    transform: translate(calc(-60%), 33%) rotate(0deg);
  }
  #scissors.cut .left {
    transform: translate(calc(-60%), 54%) rotate(24deg);
  }
  .scissor.right {
    transform: translate(calc(-40%), 33%) rotate(0deg);
  }
  #scissors.cut .right {
    transform: translate(calc(-40%), 54%) rotate(-24deg);
  }

  #scroll {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 0;
    width: 10.41vw;
    height: 5.2vw;
    margin: 0 auto;
    overflow-y: hidden;
  }

  #bg {
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    box-sizing: border-box;
    width: 100%;
    height: 200%;
    background: #fbf8f6;
    border-style: inset;
    border: 0.41vw solid #4f4f54;
    border-radius: 50%;
  }
</style>
