<script>
 

let key = "pVtPXBCbcd5uoafUYCibCAUDPbCuFqCGbjx0ZSwh";
import Guardar from './lib/Nasa.svelte';
let guardarurl = [];

async function loadNasa(){
   const respuesta = await fetch(`https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=40&api_key=${key}`);
   const data = await respuesta.json()
   guardarurl = data.photos;
}

loadNasa()

</script>

<h1>app Nasa_api</h1>


<div class="container">
 <div class="grid">
   {#each guardarurl as guardar}
   <Guardar guardar={guardar}/>
   {/each}
 </div>
</div>




