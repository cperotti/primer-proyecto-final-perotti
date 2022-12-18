<template>
  <section>
    <header>
            <nav class="navbar navbar-expand-lg bg-light">
                <div class="container-fluid">
                    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Toggle navigation">
                        <span class="navbar-toggler-icon"></span>
                    </button>
                    <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
                        <a class="navbar-brand" href="/home">GardenSHOP</a>
                        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                            <li class="nav-item dropdown">
                                <a href="#" role="button" class="nav-link dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">Productos</a>
                                <ul class="dropdown-menu">
                                    <li v-for="(producto,index) in productos" :key="index"><router-link :to="`/productos/${producto.title}`" class="dropdown-item">{{producto.title}}</router-link></li>
                                </ul>
                            </li>
                        </ul>
                        <div>
                            <button @click="logOut" class="btn btn-outline-success" type="button">Log out</button>
                        </div>
                    </div>
                </div>
            </nav>
        </header>
        <div class="container d-grid gap-3">
        <div class="row justify-content-end">
            <div class="col-2 p-3">
        <input class="form-control" type="search" placeholder="Search" aria-label="Search">
            </div>
        </div>
   <list-component />
        </div>
  </section>
</template>

<script>
// @ is an alias to /src
import ListComponent from '@/components/ListComponent.vue'

export default {
  name: 'ListView',
  components: {
    ListComponent
  },
  data() {
    return {
        productos:[
            {
                id:1,
                title:'Plantas'
            },
            {
                id:2,
                title:'Semillas'
            },
            {
                id:3,
                title:'Elemetos Jardineria'
            }
        ]
    }
  },
}
</script>