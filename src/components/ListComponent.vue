<template>
    <div>
        <div class="row">
            <card-component v-for="(producto) in productos" :key="producto.id" :producto="producto" />
        </div>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue'
import planta1 from './../assets/planta1.jpg'
import planta2 from './../assets/planta2.jpg'
import planta3 from './../assets/planta3.jpg'

export default {
  components: { CardComponent },
    name: 'ListComponent',
    data() {
        return {
            productos:[
                {
                id:1,
                name:'Calathea Sanderiana',
                descripcion: 'Planta herbácea de hoja perenne, mata de grandes hojas ovales al final de un largo pedúnculo',
                imagen: planta1,
                autorLink:"https://www.freepik.es/foto-gratis/calathea-ornata-sanderiana-maceta-naranja_19075286.htm#page=5&query=plantas&position=2&from_view=search&track=sph",
                precio:2367
                },
                {
                id:2,
                name:'Planta de serpiente',
                descripcion: 'Este es el producto 2',
                imagen:planta2,
                autorLink:"https://www.freepik.es/foto-gratis/planta-serpiente-maceta-blanca_11430473.htm#page=2&query=plantas&position=39&from_view=search&track=sph",
                precio:1943
                },
                {
                id:3,
                name:'Lirio de la paz ',
                descripcion: 'Este es el producto 3',
                imagen:planta3,
                autorLink:"https://www.freepik.es/foto-gratis/planta-lirio-paz-objeto-decoracion-hogar-maceta-terracota_19075954.htm#query=plantas&position=39&from_view=search&track=sph",
                precio:854,
                }
            ],
        }
    },
}
</script>

<style scope>
</style>