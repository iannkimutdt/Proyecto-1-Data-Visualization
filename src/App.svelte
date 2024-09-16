<!-- Script JS -->
<script>
  import * as d3 from 'd3'

  function arcGenerator({innerRadius, outerRadius, startAngle, endAngle}) {
    return d3.arc()({
      innerRadius,
      outerRadius,
      startAngle,
      endAngle,
    })
  }

  let serieA = [24, 33, 42, 54, 63, 71, 77, 87, 92, 98]
  let serieB = [23, 35, 45, 56, 50, 43, 38, 32, 28, 25]
  let años = [2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023]
</script>



<svelte:head>
<script async type='text/javascript' src= "https://public.flourish.studio/resources/embed.js" />
</svelte:head>



<!-- Estructura contenido HTML -->  
<div class="main_header_container">
  <h1 class="main_header">La carrera entre hermanos</h1>
</div>
<div>
  <h3 class="subheader">El uso de Instagram y Facebook en jóvenes de 18 a 28 años en Argentina entre 2014 y 2023</h3>
</div>

<h4 class="graficos_header">Evolución del porcentaje entre 2014 y 2023</h4>	

<div class=años_container>
  {#each años as año}
    <p id="años">{año}</p>
  {/each}
</div>

<div class="series_container">

  <!-- INSTAGRAM -->
  <div class="serie_wrapper" id="serie_Instagram">
    <img class="image_logo" src="./images/instagram_logo.png" alt="Logo Instagram"> 
    <h4 class="serie_header" style="color:#F15827">Instragram</h4>
    <div class="donas_container" id="donas_Instagram">  
      {#each serieA as nA}
        <div class="dona_wrapper">
          <svg height=100px width=100px>
            <path
              d={arcGenerator({
                innerRadius: 25,
                outerRadius: 50,
                startAngle: 0,
                endAngle: Math.PI * 2,
              })}
              fill="#ccc"
              transform="translate(50, 50)"
            />
            <path
              d={arcGenerator({
                innerRadius: 25,
                outerRadius: 50,
                startAngle: 0,
                endAngle: (nA / 100) * 2 * Math.PI,
              })}
              fill=#F15827
              transform="translate(50, 50)"
            />
          </svg>
          <p class="dona_number" style="color:#F15827"> {nA}%</p>
        </div>
      {/each}
    </div>      
  </div>

  <!-- FACEBOOK-->
  <div class="serie_wrapper" id="serie_Facebook">
    <img class="image_logo" src="./images/facebook_logo.png" alt="Logo Facebook"> 
    <h4 class="serie_header" style="color:#6285F6">Facebook</h4>
    <div class="donas_container" id="donas_Facebook">
      {#each serieB as nB}
        <div class="dona_wrapper">
          <svg height=100px width=100px>
            <path
              d={arcGenerator({
                innerRadius: 25,
                outerRadius: 50,
                startAngle: 0,
                endAngle: Math.PI * 2,
              })}
              fill="#ccc"
              transform="translate(50, 50)"
            />
            <path
              d={arcGenerator({
                innerRadius: 25,
                outerRadius: 50,
                startAngle: 0,
                endAngle: (nB / 100) * 2 * Math.PI,
              })}
              fill=#6285F6
              transform="translate(50, 50)"
            />
          </svg>
          <p class="dona_number" style="color:#6285F6"> {nB}%</p>
        </div>
      {/each}
    </div>
  </div>
</div>

<div class="descripcion">
  <p>Los jóvenes argentinos prefieren Instagram ya que ofrece una plataforma que se enfoca más en contenidos visuales.
    Tiene una mejor experiencia de usuario y es más amigable para dispositivos móviles. 
    Además, los algoritmos de Instagram son mejores para mostrar contenido único y personalizado.
  </p>
</div>

<h4 class="graficos_header">Porcentaje de uso</h4>
<div class="graficos_container">
  <div class="grafico_wrapper">
    <div class="flourish-embed flourish-chart" data-src="visualisation/19289134"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19289134/thumbnail" alt="chart visualization" /></noscript></div>
  </div>
  <div class="grafico_wrapper">
    <div class="flourish-embed flourish-heatmap" data-src="visualisation/19370192"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19370192/thumbnail" width="100%" alt="heatmap visualization" /></noscript></div>
    </div>
</div>

<div class="descripcion">
  <p>Desde el año 2017, comenzó la disminución del uso de Facebook. <br/>
    Esto se debe a que la generación de jóvenes que más utilizaba la plataforma azul empezó a buscar alternativas novedosas como Instagram.
  </p>
</div>

<h4 class="graficos_header">Variación anual</h4>
<div class="graficos_container">
  <div class="grafico_wrapper">
    <div class="flourish-embed flourish-bar-chart-race" data-src="visualisation/19370374"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19370374/thumbnail" width="100%" alt="bar-chart-race visualization" /></noscript></div>    
  </div>    
  <div class="grafico_wrapper">      
    <div class="flourish-embed flourish-chart" data-src="visualisation/19281080"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19281080/thumbnail" width="100%" alt="chart visualization" /></noscript></div>
  </div>  
</div>

<div class="descripcion">
  <p style="margin-bottom:100px">Hasta finales del año 2017, se puede observar que el crecimiento de ambos hermanos era parejo. <br/>
    Desde ese momento, la conexión a Facebook sigue disminuyendo debido también a que las nuevas generaciones la consideran "anticuada".
  </p>
</div>

<hr>

<footer class="footer">
  <p>Ian David Yong Joon Kim</p>
  <p>
    <a href="https://github.com/iannkimutdt" target="_blank">GitHub</a> |
    <a href="https://www.linkedin.com/in/iandavidyongjoonkim/" target="_blank">LinkedIn</a> |
    <a href="https://www.instagram.com/iannkim/" target="_blank">Instagram</a>
  </p>
  <p>Visualización de Datos - Universidad Torcuato Di Tella</p>
</footer>



<!-- Estilos CSS -->
<style>
  .main_header {
    font-size: 65px;
    text-align: center;
    font-weight: bold;
  }
  .subheader {
    font-size: 21px;
    text-align: center;  
  }


  .años_container {
    display: flex;
    position: relative;
    top: 15px;
    justify-content: space-around;
    width: 1050px;
    margin-left: 160px;
  }
  #años {
    font-size: 17px;
  }


  .serie_wrapper {
    display: flex;
    align-items: center;
    height: 140px;
    }
  .serie_header {
    font-size: 20px;
    margin-right: 20px;
  }
  .image_logo {
    width: 30px;
    height: 30px;
    margin-right: 10px;
  }


  .donas_container {
    display: flex;
    width: 100%;
    justify-content: space-evenly;
  }
  .dona_wrapper {
    margin-top: 50px;
    align-items: center;
  }
  .dona_number {
    position: relative;
    top: -83px;
    text-align: center;
    font-size: 17px;
    font-weight: bold;
  }
  #donas_Facebook {
    margin-left: 10px;
  }


  .descripcion {
    font-size: 17px;
    margin-top: 60px;
    text-align: center;
  }


  .graficos_header {
    font-size: 30px;
    text-align: center;
    font-weight: bold;
    margin-top: 125px;
  }
  .graficos_container {
    display: flex;
    justify-content: space-around; 
    text-align: center;
    margin-top: 30px;
  }
  .grafico_wrapper {
    width: 45%;
  }

  .footer {
    text-align: center;
    color: gray;
    font-size: 15px;
  }
  .footer a {
    color: #0077b5;
    margin: 0 3px;
    margin-top: 100px;
  }
  .footer a:hover {
    color: gray;
  }
</style>
