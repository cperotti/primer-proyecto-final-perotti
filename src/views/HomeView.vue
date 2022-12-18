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
                                    <li><router-link to="/productos/plantas" class="dropdown-item">Plantas</router-link></li>
                                    <li><router-link to="/productos/semillas" class="dropdown-item">Semillas</router-link></li>
                                    <li><router-link to="/productos/elementosJardineria" class="dropdown-item">Elementos jardineria</router-link></li>
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
    </section>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  data(){
    return{

    }
  },
  methods:{
    logOut(){
        this.$router.push('/')
    }
  }
}
</script>