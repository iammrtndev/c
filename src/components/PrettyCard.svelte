<script lang="ts">
</script>

<div class="PrettyCard">
  <div id="title">
    <slot name="title" />
  </div>
  <slot />
  <div id="bottom" />
</div>

<style>
  .PrettyCard {
    padding: 8.33vw 8.33vw 20.83vw;
    position: relative;
    border: 0.41vw solid #4f4f54;
    box-sizing: border-box;
  }

  #title {
    position: absolute;
    left: 50%;
    top: 0;
    transform: translate(-50%, -50%);
    background: #fbf8f6;
    width: 90%;
    text-align: center;
  }

  #bottom {
    position: absolute;
    left: 50%;
    bottom: 0;
    transform: translate(-50%, 50%);
    background: #fbf8f6;
    width: 90%;
    height: 100px;
  }
</style>
