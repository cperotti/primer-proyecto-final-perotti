<template>
    <div class="container-detail">
        <h3>Detalle de producto</h3>
        <div class="card mb-3">
            <div class="row g-0">
                <div class="col-md-8">
                <img :src="detalleProducto.imagen" class="img-fluid rounded-start imagen-detail" alt="img">
                <p class="card-text"><small class="text-muted"><a :href="detalleProducto.autorLink">Imagen de rawpixel.com</a> en Freepik</small></p>
                </div>
                <div class="col-md-4">
                <div class="card-body d-grid gap-2">
                    <h4 class="card-title">{{detalleProducto.name}}</h4>
                    <p class="card-text">{{detalleProducto.descripcion}}</p>
                    <h5>Caracteristicas</h5>
                    <div class="accordion accordion-flush" id="accordionFlushExample">
                        <div class="accordion-item" v-for="(detalle, index) in detalleProducto.detalle" :key="index">
                            <h2 class="accordion-header" :id="index">
                            <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" :data-bs-target="`#${detalle.titulo}`" aria-expanded="false" :aria-controls="`${detalle.titulo}`">
                                {{detalle.titulo}}
                            </button>
                            </h2>
                            <div :id="`${detalle.titulo}`" class="accordion-collapse collapse" :aria-labelledby="index" data-bs-parent="#accordionFlushExample">
                            <div class="accordion-body">{{detalle.descripcion}}</div>
                        </div>
                        </div>
                    </div>
                    <button @click="comprar(detalleProducto)" type="button" class="btn btn-primary">Comprar</button>
                </div>
                </div>
            </div>
        </div>
        <h4>Comentarios</h4>
        <div class="d-grid gap-3">
            <span>Añadir nuevo comentario</span>
            <textarea v-model="comentario" class="form-control" id="areaComentarios" placeholder="Escribi un comentario" rows="3"></textarea>
            <div class="d-flex justify-content-end">
                <button v-if="comentario" @click="guardarComentario()" type="button" class="btn btn-primary" >Comentar</button>
            </div>
        </div>
        <br/>
        <ul class="list-group" v-for="(comentario, index) in detalleProducto.comentarios" :key="index">
            <li class="list-group-item d-flex justify-content-between align-items-start">
                <div class="ms-2 me-auto">
                <div class="fw-bold">{{comentario.usuario}}</div>
                    {{comentario.comentario}}
                </div>
                <p class="card-text"><small class="text-muted">{{comentario.fechaHora}}</small></p>
            </li>
        </ul>
    </div>
</template>

<script>
import planta1 from './../assets/planta1.jpg'

export default {
    name:'DetailComponent',
    data() {
        return {
            comentario:'',
            dataCompraProducto:{
                id:'',
                nombre:'',
                precio:0,
                cantidad:''
            },
            detalleProducto:{
                name:'Calathea Sanderiana',
                descripcion:'Planta herbácea de hoja perenne, mata de grandes hojas ovales al final de un largo pedúnculo',
                detalle:[
                {
                    titulo:'Familia',
                    descripcion:'Las Calatheas pertenecen a la familia de las Marantaceae.',
                    expanded:'true'
                },
                {
                    titulo:'Origen',
                    descripcion:'Su origen se encuentra en Ecuador y Brasil',
                    expanded:'false'
                },
                {
                    titulo:'Mantenimiento',
                    descripcion:'Al ser plantas que provienen de los bosques tropicales, la situación y cuidados ha de ser lo más parecido, para ello no las pondremos al sol. La tierra ( turba, arena y hojas descompuestas ) ha de ser suelta, fértil y con un buen drenaje. El abonado ha de ser frecuente, cada 15 o 20 días pero en bajas cantidades. El sustrato no ha de estar seco, más bien mantenerlo con  una ligera humedad. Conviene pulverizar las hojas con frecuencia con agua de buena calidad sin cal  y a temperatura ambiente. El ambiente ha de ser cálido, no más de 22 grados y no menos de 15.',
                    expanded:'false'
                },
                {
                    titulo:'Plagas',
                    descripcion:'Suelen ser muy resistentes a las enfermedades, ocasionalmente algún problema de hongos, también se pueden presentar manchas en las puntas y los bordes de las hojas por falta de humedad ambiental. Puede recibir algún ataque de araña roja.',
                    expanded:'false'
                },
                {
                    titulo:'Multiplicación',
                    descripcion:'Cuando la planta ya tiene después de unos años un buen sistema radicular ( produce raíces gordas como rizomas ) y los tiestos de plástico se deforman por esas raíces, podemos dividirla en varios trozos y con cada uno de ellos tener una nueva planta. También se pueden intentar reproducir por esqueje aunque es un poco difícil.',
                    expanded:'false'
                },
                {
                    titulo:'Curiosidades',
                    descripcion:'Su nombre proviene del griego, calathos= cesta y algunos indígenas usan sus hojas para hacer cestas y para cubrir los techos de sus cabañas. La calathea es una planta con un ritmo de día y otro de noche. Sus hojas se mueven,  los tropismos o movimientos de las plantas son factores para adaptarse a las condiciones del ambiente que más les favorece. Así si hay un exceso de luz se levantan o enrollan sobre si mismas para exponer menos superficie a la luz y lo contrario, captan más luz extendiendo sus hojas y colocándolas horizontalmente. Para ello las calatheas usan una articulación en la base de los pecíolos de las hojas. Por medio de permeabilidad de las membranas celulares ante las sales, aumentan o disminuyen la turgencia o presión y consiguen este movimiento, provocando las mas de las veces incluso un ruido perfectamente audible.',
                    expanded:'false'
                }
                ]
                ,
                imagen: planta1,
                autorLink:"https://www.freepik.es/foto-gratis/calathea-ornata-sanderiana-maceta-naranja_19075286.htm#page=5&query=plantas&position=2&from_view=search&track=sph",
                comentarios:[
                {
                    usuario:'Jorge',
                    fechaHora:'8/12/22 20:30hs',
                    comentario:'Muy linda planta, es super sencillo cuidarla',
                },
                {
                    usuario:'Maria',
                    fechaHora:'8/12/22 19:30hs',
                    comentario:'Me gusto la informacio que brindó la web para saber mas sobre esta planta, me ayudo a poder cuidarla.',
                }
                ],
                precio:854
            },
        }   
    },
    methods:{
        guardarComentario(){
            this.detalleProducto={
                ...this.detalleProducto,
                comentarios:[
                    ...this.detalleProducto.comentarios,
                    {
                        usuario:'Carolina',
                        fechaHora:new Date(),
                        comentario: this.comentario
                    }
                ]
            }
            this.comentario=''
        },
        comprar(detalleProducto){
            console.log(detalleProducto)
            
        }
    }
}
</script>

<style scope>
.container-detail{
    margin-bottom: 24px;
    padding: 15px;
}
</style>