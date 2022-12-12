<template>
    <div class="col">
        <div class="card">
            <img :src="producto.imagen" class="card-img-top imagen" alt="img">
            <p class="card-text"><small class="text-muted"><a :href="producto.autorLink">Imagen de rawpixel.com</a> en Freepik</small></p>
            <div class="card-body">
                <h5 class="card-title">{{producto.name}}</h5>
                <p class="card-text">Precio ${{producto.precio}}</p>
                <div class="d-flex justify-content-between">
                <button type="button" class="btn btn-outline-primary">Ver detalle</button>
                <button type="button" class="btn btn-primary">Comprar</button>
                </div>
            </div>
        </div>
    </div>
  
</template>

<script>
export default {
    name:'CardComponent',
    props:{
        producto: Object,
    },
    data() {
        return {
            
        }
    },
}
</script>

<style>
.imagen{
    max-height: 80vh;
}
</style>