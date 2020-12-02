<template>
  <div align="left">
    <div id="modificadores" >
      <div class="form-group">
        <label for="color">Color:  </label>
        <input 
          type="text"
          id="color"
          class="form-group"
          style= "width:300px"
          v-model="color"
        >
      </div>
    
      <div class="form-group">
        <label for="fondo"><h6>Fondo: </h6></label>
        <input 
          type="text"
          id="fondo"
          class="form-group"
          style="width:300px"
          v-model="fondo"
        >
      </div>

      <div class="form-group">
        <label for="size"><h6>Size: </h6></label>
        <input 
          type="text"
          id="size"
          class="form-group"
          style="width:300px"
          v-model="size"
        >
      </div>

    </div>
    
    <hr />
    
    <div for="form-group">
      <label for="texto"><h6>Texto: </h6></label>
      <input 
        type="text"
        id="texto"
        class="form-group"
        :style="{
          color: color,
          'background-color': fondo,
          'font-size': size   
        }"
        v-model="texto"
      >
    </div>

    <div v-if="cantPalabras">
      <p>Cantidad de palabras {{cantPalabras}}</p>
    </div>

    &nbsp;&nbsp;
    &nbsp;&nbsp;

    <table class="table text-left"> 
      <tr>
        <th scope="col">Número de pregunta</th>
        <th scope="col">Respuesta</th>
      </tr>
      <tr>
        <td scope="col"> <p>1</p> </td>
        <td scope="col"> <p>b</p> </td>
      </tr>
      <tr>
        <td scope="col"> <p>2</p> </td>
        <td scope="col"> <p>c</p> </td>
      </tr>
      <tr>
        <td scope="col"> <p>3</p> </td>
        <td scope="col"> <p>b</p> </td>
      </tr>
      <tr>
        <td scope="col"> <p>4</p> </td>
        <td scope="col"> <p>d</p> </td>
      </tr>
      <tr>
        <td scope="col"> <p>5</p> </td>
        <td scope="col"> <p>d</p> </td>
      </tr>
    </table>
  </div>
</template>

<script>
  
  export default {
    name: 'Texto',
    data() {
      return {
        color: '',
        fondo: '',
        size: '',
        texto: ''
      }
    },
    computed: {
      cantPalabras() {
        let arrayTexto = this.texto.trim()
        let cant = 0
        if (arrayTexto != '') {
          arrayTexto = arrayTexto.replace(/[ ]+/g, " ")
          arrayTexto = arrayTexto.split(" ")
          cant = arrayTexto.length
        }
        console.log(cant);
        return cant
      }
    }
  }
</script>

<style scoped>

</style>
