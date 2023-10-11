<script>
    import PanelLengua from "./Panel-lengua.svelte";


</script>

<div class="container">
    <h1>SOBRE EL PROYECTO</h1>
    <p>El siguiente montaje digital se creó a partir de una versión previamente publicada en formato físico <a href='https://editorial.urosario.edu.co/gpd-el-montaje-en-aby-warburg-y-en-walter-benjamin-un-metodo-alternativo-para-la-representacion-de-la-violencia.html' target="_blank">(Urueña, 2017)</a>. Se utilizó el lenguaje de las Humanidades digitales para reconceptualizar el ejercicio como una visualización de datos humanísticos. Para ello, se desarrolló una pequeña base de datos con las imágenes del montaje y se construyó una narración interactiva que permite explorar las imágenes haciendo clic en sus áreas correspondientes. Esta visualización se realizó mediante la librería de narraciones interactivas <a href="https://srsergiorodriguez.github.io/aventura-interactiva/" target="_blank">Aventura.js</a>, adaptada en esta ocasión para crear una narración iconográfica que captura la forma compositiva del montaje y las variaciones visuales del Corte de Corbata.</p>
    </div>

<style>

    .container {
            
            font-family: 'Public Sans', sans-serif;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto; /* Centrar horizontalmente el contenido */
            padding: 80px;
            background-color: #faf8ff;
            border: solid 1px #363636;
            text-align: justify;
            color: #363636;
        }

        /* .container img {
            width: 100%;
        } */
    
        h1 {
            margin-bottom: 10px;
            font-size: 3vw;
            font-weight: 400;
            color: #8685ef;
        }
    
        p {
            font-size: 16px;
            margin-bottom: 10px;
        }

    
        a {
            color: #8685ef;
            text-decoration: none;
        }
    
        a:hover {
            text-decoration: underline;
        }
    
        /* .img-montaje {
            display: flex;
            flex-direction: row;
            width: 100%;
            justify-content: space-between;
        } */
    @media (max-width: 768px) {

    
    .container {
      max-width: 100%;
      padding: 3vw;
    }
      }
    
    </style>