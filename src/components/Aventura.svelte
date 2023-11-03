<script>
    import { onMount } from 'svelte';
    import { aventura1 } from "../stores/aventura1";
    import * as d3 from 'd3';
    
    export let pathEscenas;
    export let escenaInicial; 
  
    // let urlString = "https://lh3.googleusercontent.com/d/";
    let path = "assets/imgs/";
    let ready = false;
  
  
  
    
  
    onMount (async() => {
      await testAventura();
    });
  
    async function testAventura() {
      const options = {
        adventureContainer: "aventura-container",
        adventureSlide: false,
        typewriterSpeed: 0,
        evalTags: true,
        vizImageSize: 70,
        urlWord: "Repositorio",
        vizWidth: 1000,
        vizHeight: 1000
      }
  
      const a = new $aventura1('es', options);
      console.log(pathEscenas);
      const escenas = await a.cargarJSON(pathEscenas);
      const datos = await d3.csv('https://docs.google.com/spreadsheets/d/e/2PACX-1vSBgKPIeBgDxdkT2laFTEwaN1FkEFVxW9tTVsPj1qiVXgSBIluJwKIHXSDva52ST1RQQvkeC7lMCCxl/pub?output=csv', (d => ({
            ...d,
            ID: d.n,
            IMGURL: path + d.src,
            // IMGURL: urlString + d.id
  
          })))
   
          console.log(datos);
    
          await a.setDataScenes(escenas, datos, ["obra", "autor", "fecha", "tecnica", "fuente"]);
          a.iniciarAventura(escenaInicial);
          ready = true;
        };
    
  </script>
  
  <div id="aventura-container"></div>
  {#if !ready}
  <div class="loader"><img src="assets/logo/loading.gif" alt="cargando"></div>
  {/if}
  
  
  <style>
      #aventura-container {
          margin-top: 2vw;
      }
  
      .loader {
       display: flex;
       justify-content: center;
       align-items: center; 
      }
  
      @media (max-width: 768px) {
  .loader img {
    max-width: 100%;
  }
  
    }
  
  </style>
  