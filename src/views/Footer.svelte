<script>
  import phone from 'src/assets/phone.png'
  import fix from 'src/assets/fix.png'
  import map from 'src/assets/map.png'
  import gmail from 'src/assets/gmail.png'
  import facebook from 'src/assets/facebook.png'
  import instagram from 'src/assets/instagram.png'
</script>

<div class="Footer">
  <h2>Nous Joindre</h2>
  <footer>
    <img src={map} id="map" alt="" />
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
      <a href="https://www.facebook.com/">
        <img src={facebook} alt="" />
      </a>
      <a href="https://www.instagram.com/">
        <img src={instagram} alt="" />
      </a>
      <a href="https://www.twitter.com/">
        <img src={gmail} alt="" />
      </a>
    </div>
  </footer>
</div>

<style>
  .Footer {
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

  #map {
    position: absolute;
    bottom: 4.16vw;
    left: 12.5vw;
    width: 37.5vw;
  }

  h2 {
    color: #290001;
    font-size: 6.66vw;
    font-weight: normal;
    margin-left: 52.08vw;
  }

  .tel a {
    font-size: 1.66vw;
    color: #fbf8f6;
    text-align: right;
    flex: 1;
  }

  p {
    color: #fbf8f6;
    font-size: 1.66vw;
    margin-bottom: 1.04vw;
  }

  .tel {
    width: 12.5vw;
    display: flex;
    margin-bottom: 1.04vw;
  }

  #phone {
    width: 1.25vw;
    height: auto;
  }

  #fix {
    width: 1.66vw;
    height: auto;
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
