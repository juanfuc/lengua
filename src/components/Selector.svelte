<script>
    export let secciones;
    export let pagina;

    function handleClick(i) {
        pagina = i;
    }

</script>

{#each secciones as sec, i }
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    <nav><ul><li><h3 class="menu" on:click={() => handleClick(i)}>{sec.seccion}</h3></li></ul></nav>
{/each}
<style>
.menu {
    margin-right: 20px;
    margin-top: 20px;
}
    nav ul {
        list-style: none;
        user-select: none;      
    }

    nav ul li:hover {
        color: #8685ef;
        user-select: none;
    } 
    
</style>