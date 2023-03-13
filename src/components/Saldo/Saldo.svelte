<span>
    {icono} {importe} €
</span>

<script>
    export let importe = 0
    let icono

    $: {
        if (importe < 0) icono = "🏴‍☠️"
        if (importe === 0) icono = "👌"
        if (importe > 0) icono = "💰"
    }

</script>