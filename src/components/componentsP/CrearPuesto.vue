<template>
    <div class="container-fluid">
        <div class="card" style="background-color: #333333;">
          <div class="card-header" style="background-color: #2E8B57; color: white;">Crear Puesto</div>
            <div style="background-color: #333333;" class="card-body">
                <form v-on:submit.prevent="formulario">
                    <div class="row">
                        
  
                            <div class="form-group">
                                <label for="nombre" style="color: white;">Nombre:</label>
                                <input type="text" class="form-control" name="nombre" aria-describedby="helpId" id="nombre"
                                    placeholder="usuario" v-model="Puestos.nombre" />
                          
                            </div>
                        
                        
  
                    </div>
                        
                    
                    <br>
                    <div class="row">
                        <div class="btn-group" role="group" id="botonesopcion">
                            <button type="submit" class="btn btn-outline-primary">Agregar</button>
                            <router-link :to="{ name: 'listapuesto' }" class="btn btn-outline-danger">Cancelar</router-link>
                        </div>
                        <router-link :to="{ name: 'listapuesto' }" class="btn btn-outline-primary" id="finaliza" style="display: none;">Finalizar</router-link>
                    </div>
                    <br>
                    <div class="row">
                        <div id="alert" style="display:none;" class="alert alert-success" role="alert">
                            {{ smg }}
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
  </template>
  <style>
  .card-body {
      margin: 2em;
  }
  </style>
  <script>
  import axios from 'axios';
  export default {
    name: "crearPuesto",
    components: {
  
    },
  
    data() {
        return {
            Puestos: {},
            smg: "",
        };
    },
    methods: {
        formulario() {
            var cuerpo = {
                nombre: this.Puestos.nombre
            };
  
            axios.post('https://localhost:7051/Puesto', cuerpo).then((result) => {
  
                if (result.status == 200) {
                    document.getElementById("alert").style.display = "block";
                    document.getElementById('botonesopcion').style.display="none";
                    this.smg = "Se creo correctamente";
                    document.getElementById('finaliza').style.display="block";
                    console.log(result);
                }
                // window.location.href = "dashboard";
  
            })
        }
    }
  }
  </script>
  
  <!-- <style scoped>
  label {
    font-weight: bold;
  }
  </style> -->