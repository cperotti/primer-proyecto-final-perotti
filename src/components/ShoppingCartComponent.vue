<template>
    <div class="container-carrito">
        <h3>Carrito de compras</h3>
        <table class="table table-light table-bordered">
            <thead>
                <tr>
                    <th>Identificación</th>
                    <th>Nombre</th>
                    <th>Precio</th>
                    <th>Cantidad</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(producto, index) in productosSeleccionados" :key="index">
                    <td>{{producto.id}}</td>
                    <td>{{producto.nombre}}</td>
                    <td>${{producto.precio}}</td>
                    <td><button @click="decrementarCantidad" type="button" class="btn btn-primary" >-</button> {{producto.cantidad}} <button @click="incrementarCantidad" type="button" class="btn btn-primary">+</button></td>
                </tr>
            </tbody>
        </table>
    </div>
  
</template>

<script>
export default {
    name:'ShoppingCartComponent',
    data() {
        return {
            productosSeleccionados:[
                {
                    id:1,
                    nombre:'Calathea Sanderiana',
                    precio:2367,
                    cantidad:1,
                },
                {
                    id:2,
                    nombre:'planta de serpiente',
                    precio:1943,
                    cantidad:1,
                }
            ]
        }
    },
    methods:{
        decrementarCantidad(){
        },
        incrementarCantidad(){
        }

    }
}
</script>

<style scope>
.container-carrito{
    margin-bottom: 24px;
    padding: 15px;
}
</style>