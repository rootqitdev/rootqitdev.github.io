<script>
  import { onMount } from 'svelte';
  import AperolSpritz from './assets/Aperol-Spritz1080.png'
  import BeAperolSpritz from './lib/BE_AperolSpritz.svelte';
  import LimoncelloSpritz from './assets/Limoncell-Spritz1080.png'
  import BeLemoncelloSpritz from './lib/BE_LemoncelloSpritz.svelte';
  import PinaColada from './assets/Pina-Colada1080.png'
  import BePinaColada from './lib/BE_PinaColada.svelte';
  import StrawberryLimes from './assets/Erdbeer-Limes1080.png'
  import BeStrawberryLimes from './lib/BE_StrawberryLimes.svelte';
  import LilletWildberry from './assets/Lillet-Wildberry1080.png'
  import BeLilletWildberry from './lib/BE_LilletWildberry.svelte'
  import Kiba from './assets/Kiba1080.png'
  import BeKiba from './lib/BE_Kiba.svelte';
  import Bier from './assets/Bier1080.png'
  import BeBier from './lib/BE_LilletWildberry.svelte';
  import Espresso from './assets/Espresso1080.png'
  import BeEspresso from './lib/BE_Espresso.svelte';
  import Cappucino from './assets/Cappucion1080.png'
  import BeCappucino from './lib/BE_Cappucino.svelte';
  import {Notifications, acts} from '@tadashi/svelte-notification'
    


  let images = [
    { src: AperolSpritz, alt: 'Aperol Spritz', component: BeAperolSpritz },
    { src: Kiba, alt: 'KiBa', component: BeKiba },
    { src: PinaColada, alt: 'Pina Colada', component: BePinaColada },
    { src: LilletWildberry, alt: 'Lillet Wildberry', component: BeLilletWildberry },
    // { src: Water, alt: 'Wasser', component: BeWater },
    // { src: Bier, alt: 'Bier', component: BeBier },
    // { src: Espresso, alt: 'Espresso', component: BeEspresso },
    // { src: Cappucino, alt: 'Cappucino', component: BeCappucino }
  ];

  
</script>

<h1>BestellMenü</h1>

<div class="container">
  <div class="grid">
    {#each images as image, i}
      <div class="grid-item">
        <img src={image.src} alt={image.alt} />
        <h2>{image.alt}</h2>
        <svelte:component this={image.component} />
      </div>
    {/each}
  </div>
</div>

<style>
  h1 {
    font-size: 2.5rem;
    margin-bottom: 2rem;
    text-align: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: #242424;
    padding: 1rem 0;
    z-index: 1000;
  }

  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding-top: 5rem; /* Add space for the fixed header */
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* 2x4 grid */
    gap: 2rem;
    max-width: 90vw; /* Limit the maximum width of the grid */
  }

  .grid-item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  img {
    width: 100%; /* Make the image fill its container */
    height: auto; /* Maintain aspect ratio */
    max-width: 45vw; /* Limit the maximum width of the image */
    max-height: 45vw; /* Limit the maximum height of the image */
    object-fit: cover; /* Ensure the image covers the entire area */
    border-radius: 8px;
  }

  h2 {
    margin: 1rem 0;
    font-size: 1.5rem;
  }

  /* button {
    background-color: #333;
    color: #fff;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  button:hover {
    background-color: #555;
  } */
</style>
