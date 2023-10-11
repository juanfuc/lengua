<script>
    import PanelLengua from "../components/Panel-lengua.svelte";
    import Selector from "../components/Selector.svelte";
    import Teoria from "../components/Teoria.svelte";
    import Sobre from "../components/Sobre.svelte";
    import Panel from "../components/Panel.svelte";

    let secciones = [
        {seccion: "PANEL", component:Panel},    
        {seccion: "ACERCA", component:Sobre},
        {seccion: "¿MONTAJE?", component:Teoria}
    ]

    let pagina = 0;
    let mostrarPanelLengua = true;

    $: componenteActual = secciones[pagina].component;

</script>

<div class="contenedor-general">
    <header class="header"><div id="titulo"><h1>Montaje del Corte de Corbata</h1></div><nav class="textos-menu"><Selector {secciones} bind:pagina/></nav></header>
   <div class="contenido">
    <div class="panel">
        {#if pagina == 0 && mostrarPanelLengua}
            <PanelLengua/>
        {/if}
    </div>

        <div class="contenedor-menu">
        <!-- svelte-ignore empty-block -->
        {#if pagina == 0}
            <Panel/>
        {:else if  pagina == 1}
           <Sobre/>
        {:else if pagina == 2}
            <Teoria/>
        {/if}
        </div>
    </div>
</div>

<style>
    /* 
        nav {
            background-color: black;
        } */
    

        .contenedor-general {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .header {
            display: flex;
            justify-content: space-around;
            align-items: baseline;
            background-color: #faf8ff;
            width: 100%;
            padding: 12px;
        }

        .textos-menu {
            display: flex;
            justify-content: space-around;
            cursor: pointer;
            color: #363636;
            font-size: .7em;
            font-family: 'Public Sans', sans-serif;
            text-align: center;
            max-width: 100%;
            overflow-x: auto;
            font-weight: 800;
        }
        .contenedor-menu {
            margin-top: 8%;
        }
    
       #titulo h1 {
      
            color: #363636;
            /* background-color: rgb(225, 101, 38); */
            font-size: 1.4em;
            font-weight: 600;
            font-family: 'Public Sans', sans-serif;
        }
    
        /* Estilos para pantallas pequeñas (móviles) */
    @media screen and (max-width: 768px) {
        .header {
            flex-direction: column;
            align-items: center;
        }
    

        #titulo h1 {
            font-size: 1.2em; /* Ajusta el tamaño del título para móviles */
            margin-bottom: 10px; /* Agrega un margen inferior para separar el título del menú */
        }
    
        .textos-menu {
            font-size: 0.6em; /* Ajusta el tamaño del texto del menú para móviles */
            display: flex;
            justify-content: space-between;
        }
    
    }
    
    </style>

