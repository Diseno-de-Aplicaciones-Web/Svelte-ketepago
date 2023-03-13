<li>
    <label>
        🧑<input
            type="text"
            placeholder="Nombre de fulanit@..."
            bind:value={nombre}
        />
    </label>
    <label>
        💸<input
            type="number"
            placeholder="€ pagados por fulanit@..."
            bind:value={importeSatisfecho}
        />
    </label>
    <Saldo importe={saldoPendiente} />
</li>

<script>
    import { redondea } from "../../lib/auxiliar";
    import Saldo from "../Saldo/Saldo.svelte";

    export let deuda = 0

    let nombre = ""
    let importeSatisfecho = 0
    let saldoPendiente = 0

    $: saldoPendiente = redondea(importeSatisfecho - deuda)

</script>