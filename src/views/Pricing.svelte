<script>
  import PrettyCard from 'src/components/PrettyCard.svelte'

  const sections = [
    {
      title: 'Coiffure Féminin',
      pricing: [
        { name: 'Shampooing - Coupe - Brushing', price: '38€' },
        { name: 'Shampooing - Brushing', price: '29€' },
        {
          name: 'Shampooing - Coupe - Brushing - Couleur - Soin offert',
          price: '77€',
        },
        { name: 'Shampooing - Brushing - Couleur - Soin offert', price: '68€' },
        {
          name: 'Shampooing - Coupe - Brushing Mèches / Balayage tête entière - Soin offert',
          price: '103€',
        },
        {
          name: 'Shampooing - Brushing Mèches / Balayage tête entière - Soin offert',
          price: '94€',
        },
        {
          name: 'Shampooing - Coupe - Coiffage Permanente tête entière - Soin offert',
          price: '84€',
        },
        {
          name: 'Shampooing - Coiffage Permanente tête entière - Soin offert',
          price: '75€',
        },
      ],
    },
    {
      title: 'Coiffure Masculin',
      pricing: [
        { name: 'Shampooing - Coupe - Coiffage', price: '28€' },
        { name: 'Shampooing - Coupe - Tondeuse', price: '25€' },
        { name: 'Shampooing - Brushing', price: '23€' },
        { name: 'Shampooing - Coupe - Coiffage - Couleur', price: '67€' },
        { name: 'Shampooing - Coupe - Coiffage - Permanente', price: '74€' },
        { name: 'Shampooing - Coupe couronne', price: '20€' },
        { name: 'Barbe (taille)', price: '8€' },
      ],
    },
    {
      title: 'Coiffure Enfant (-10 ans)',
      pricing: [
        { name: 'Garçon : Shampooing - Coupe - Coiffage', price: '20€' },
        { name: 'Fille : Shampooing - Coupe - Coiffage naturel', price: '20€' },
        {
          name: 'Fille : Shampoing - Coupe - Brushing / Boucles',
          price: '25€',
        },
      ],
    },
  ]
</script>

<div id="Pricing">
  <PrettyCard>
    <h1 slot="title">Nos Tarifs</h1>

    {#each sections as section}
      <section>
        <h2>{section.title}</h2>
        {#each section.pricing as pricing}
          <article>
            <div class="name">{pricing.name}</div>
            <div class="line" />
            <div class="price">{pricing.price}</div>
          </article>
        {/each}
      </section>
    {/each}
  </PrettyCard>
</div>

<style>
  h1 {
    font-weight: normal;
    font-size: 6vw;
    color: #290001;
  }

  section {
    margin-bottom: 4.5vw;
  }

  h2 {
    font-weight: normal;
    font-size: 4.5vw;
    margin-bottom: 1.5vw;
    color: #290001;
  }

  article {
    font-size: 1.8vw;
    display: flex;
    align-items: center;
  }

  article + article {
    margin-top: 0.9vw;
  }

  .line {
    flex: 1;
    height: 0.1vw;
    background: #290001;
    margin: 0 3vw;
  }

  .price {
    font-size: 2.4vw;
    width: 6vw;
  }
</style>
