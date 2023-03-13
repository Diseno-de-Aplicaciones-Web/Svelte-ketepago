<main>

  <h1>Ketepago - Svelte</h1>

  <label>
    🫰<input type='number' bind:value={totalAPagar}/>
  </label>
  <label>
    🧑🏻‍🤝‍🧑🏿<input type="range" min="2" max="10" bind:value={numeroDeParticipantes}/>
  </label>

  {#each {length: numeroDeParticipantes} as _}
    <Aportacion deuda={importePorPersona}/>
  {/each}

  <h2>Tests Saldo</h2>
  <Saldo importe={-1}/>
  <Saldo importe={0}/>
  <Saldo importe={+1}/>
  
  <h2>Tests Aportacion</h2>
  <Aportacion deuda={100}/>

</main>

<script>
  import Aportacion from "./components/Aportacion/Aportacion.svelte";
  import Saldo from "./components/Saldo/Saldo.svelte";
  import { redondea } from "./lib/auxiliar";

  let totalAPagar = 0
  let numeroDeParticipantes = 2
  let importePorPersona = 0

  $: {
    importePorPersona = redondea(totalAPagar/numeroDeParticipantes)
  }

</script>
