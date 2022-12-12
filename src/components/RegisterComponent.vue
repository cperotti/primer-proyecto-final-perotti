<template>
    <div class="container-register">
    <h3>Registro</h3>
    <div class="card" style="max-width: 30rem;">
        <div class="card-header">
        Registrarte
        </div>
        <div class="card-body">
            <form @submit.prevent="validarRegistro">
                <div class="mb-3">
                    <label for="nombre" class="form-label">Nombre</label>
                    <input v-model="nombre" placeholder="Ingresa tu nombre" type="text" class="form-control" id="nombre" aria-describedby="emailHelp">
                    <p v-if="errorsRegistro.nombre" class="card-text"><small class="text-danger">{{errorsRegistro.nombre}}</small></p>
                </div>
                <div class="mb-3">
                    <label for="apellido" class="form-label">Apellido</label>
                    <input v-model="apellido" placeholder="Ingresa tu apellido" type="text" class="form-control" id="apellido">
                    <p v-if="errorsRegistro.apellido" class="card-text"><small class="text-danger">{{errorsRegistro.apellido}}</small></p>
                </div>
                <div class="mb-3">
                    <label for="email" class="form-label">Email</label>
                    <input v-model="email" placeholder="Ingresa tu email" type="email" class="form-control" id="email">
                    <p v-if="errorsRegistro.email" class="card-text"><small class="text-danger">{{errorsRegistro.email}}</small></p>
                </div>
                <div class="mb-3">
                    <label for="contrasena" class="form-label">Contraseña</label>
                    <input v-model="password" placeholder="Ingresa una contraseña" type="password" class="form-control" id="contrasena">
                    <p v-if="errorsRegistro.password" class="card-text"><small class="text-danger">{{errorsRegistro.password}}</small></p>
                </div>
                <div class="mb-3">
                    <label for="repetirContrasena" class="form-label">Repetir contraseña</label>
                    <input v-model="passwordRepeat" placeholder="Ingresa nuevamente la contraseña" type="password" class="form-control" id="repetirContrasena">
                    <p v-if="errorsRegistro.passwordRepeat" class="card-text"><small class="text-danger">{{errorsRegistro.passwordRepeat}}</small></p>
                </div>
                <div class="d-flex justify-content-end">
                    <button type="submit" class="btn btn-primary">Registrarte</button>
                </div>
            </form>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'RegisterComponents',
    data() {
        return {
            nombre:'',
            apellido:'',
            email:'',
            password:'',
            passwordRepeat:'',
            errorsRegistro:{
                nombre:'',
                apellido:'',
                email:'',
                password:'',
                passwordRepeat:''
            }
        }
    },
    methods:{
        validarRegistro(){
            if(!this.nombre){
                this.errorsRegistro = {...this.errorsRegistro, nombre:'Debes colocar tu nombre para poder registrarte'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, nombre:''} 
            }

            if(!this.apellido){
                this.errorsRegistro = {...this.errorsRegistro, apellido:'Debes colocar tu apellido para poder registrarte'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, apellido:''} 
            }

            if(!this.email){
                this.errorsRegistro = {...this.errorsRegistro, email:'Debes colocar un email para poder registrarte'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, email:''} 
            }

            if(!this.password){
                this.errorsRegistro = {...this.errorsRegistro, password:'Debes colocar una contraseña para poder registrarte'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, password:''} 
            }

            if(!this.passwordRepeat){
                this.errorsRegistro = {...this.errorsRegistro, passwordRepeat:'Debes repetir tu contraseña para poder registrarte'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, passwordRepeat:''} 
            }

            if(this.password !== this.passwordRepeat){
                this.errorsRegistro = {...this.errorsRegistro, passwordRepeat:'La contraseña no coincide con la que ingresaste'} 
            }else{
                this.errorsRegistro = {...this.errorsRegistro, passwordRepeat:''} 
            }
        }
    }
}
</script>

<style scope>
    .container-register{
        margin-bottom: 24px;
        padding: 15px;
    }
</style>