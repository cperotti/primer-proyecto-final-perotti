<template>
    <div class="d-flex justify-content-center align-items-center flex-column container-login">
    <h3>Login</h3>
    <div class="card" style="max-width: 30rem;">
        <div class="card-header">
        Iniciar sesion
        </div>
        <div class="card-body">
            <form @submit.prevent="validarLogin">
                <div class="mb-3">
                    <label for="loginEmail" class="form-label">Email</label>
                    <input v-model="email" placeholder="Ingresa tu email" type="email" class="form-control" id="loginEmail" aria-describedby="emailHelp">
                    <p v-if="errors.email" class="card-text"><small class="text-danger">{{errors.email}}</small></p>
                </div>
                <div class="mb-3">
                    <label for="loginContrasena" class="form-label">Contraseña</label>
                    <input v-model="password" placeholder="Ingresa tu contraseña" type="password" class="form-control" id="loginContrasena">
                    <p v-if="errors.password" class="card-text"><small class="text-danger c">{{errors.password}}</small></p>
                </div>
                <div class="d-flex justify-content-between">
                    <div><span>Aun no tenes una cuenta?</span><button type="button" class="btn btn-link">Registrarte</button></div>
                    <button type="submit" class="btn btn-primary">Ingresar</button>
                </div>
            </form>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: 'LoginComponent',
    data() {
        return {
            email:'',
            password:'',
            errors:{
                email:'',
                password:''
            }
        }
    },
    methods:{
        validarLogin(){
            if(!this.email){
                this.errors = {...this.errors, email:'Debes colocar un email para poder ingresar'} 
            }else{
                this.errors = {...this.errors, email:''} 
            }
            if(!this.password){
                this.errors = {...this.errors, password:'Debes colocar una contraseña para poder ingresar'} 
            }else{
                this.errors = {...this.errors, password:''} 
            }
        }
    }
}
</script>

<style scope>
.container-login{
    margin-bottom: 24px;
    padding: 15px;
}
</style>