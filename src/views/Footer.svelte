<script>
  import phone from 'src/assets/phone.png'
  import fix from 'src/assets/fix.png'
  import gmail from 'src/assets/gmail.png'
  import facebook from 'src/assets/facebook.png'
  import instagram from 'src/assets/instagram.png'
  import Mapbox from 'src/components/Mapbox.svelte'
</script>

<div id="Footer">
  <h2>Nous Joindre</h2>
  <footer>
    <div id="map">
      <Mapbox />
    </div>
    <p>Ouvert tous les jours de <b>10h à 18h</b></p>
    <p>Champ de Mars, 5 Av. Anatole France, 75007 Paris</p>
    <div class="tel">
      <img src={phone} id="phone" alt="" />
      <a href="tel:0607080910">06 07 08 09 10</a>
    </div>
    <div class="tel">
      <img src={fix} id="fix" alt="" />
      <a href="tel:0123456789">01 23 45 67 89</a>
    </div>
    <div id="socials">
      <a
        href="https://www.facebook.com/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <img src={facebook} alt="" />
      </a>
      <a
        href="https://www.instagram.com/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <img src={instagram} alt="" />
      </a>
      <a href="mailto:" target="_blank" rel="noopener noreferrer">
        <img src={gmail} alt="" />
      </a>
    </div>
  </footer>
</div>

<style>
  #Footer {
    position: relative;
    z-index: 1;
    margin-top: -4.16vw;
  }

  footer {
    position: relative;
    padding: 4.16vw 0 0 54.16vw;
    background: #290001;
    height: 29.16vw;
  }

  h2 {
    color: #290001;
    font-size: 6vw;
    font-weight: normal;
    margin-left: 52.08vw;
  }

  #map {
    position: absolute;
    bottom: 4.16vw;
    left: 13vw;
    width: 37.5vw;
    height: 33.33vw;
    outline:  0.41vw solid #fbf8f6;
  }

  .tel a {
    display: inline-flex;
    font-size: 1.66vw;
    color: #fbf8f6;
    text-align: right;
    flex: 1;
    margin-left: 0.62vw;
  }

  p {
    color: #fbf8f6;
    font-size: 1.66vw;
    margin-bottom: 1.04vw;
  }

  .tel {
    margin-bottom: 1.04vw;
  }

  #phone {
    width: 1.25vw;
  }

  #fix {
    width: 1.66vw;
  }

  #socials {
    display: flex;
    width: 33.33vw;
    margin-top: 4.16vw;
  }

  #socials a {
    margin-right: 4.16vw;
  }

  #socials img {
    height: 4.16vw;
  }
</style>
