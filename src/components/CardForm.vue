<script>
export default {
  name: 'CardForm',
  data() {
    return {
      tituloTarjeta: '',
      chipSRC: '',
      numeroTarjeta: '',
      fechaExpiracion: '',
      nombrePropietario: '',
      tipoTarjeta: ''
    }
  }
}
</script>

<template>
  <form>
    <div>
      <label>Título de la tarjeta: </label>
      <input type="text" v-model="tituloTarjeta" />
    </div>

    <div>
      <label>Chip SRC: </label>
      <select v-model="chipSRC">
        <option value="/chip.png">Golden</option>
        <option value="/silverchip.png">Silver</option>
      </select>
    </div>

    <div>
      <label>Número: </label>
      <input type="text" v-model="numeroTarjeta" />
    </div>

    <div>
      <label>Fecha de expiración: </label>
      <input type="text" v-model="fechaExpiracion" />
    </div>

    <div>
      <label>Propietario: </label>
      <input type="text" v-model="nombrePropietario" />
    </div>

    <div>
      <label>Tipo de tarjeta SRC: </label>
      <select v-model="tipoTarjeta">
        <option value="/visa.png">Visa</option>
        <option value="/mastercard.svg">Mastercard</option>
      </select>
    </div>
  </form>

  <div class="carnet">
    <h3>{{ tituloTarjeta }}</h3>
    <img width="40" :src="chipSRC" alt="" />
    <div>
      <h2>{{ numeroTarjeta }}</h2>
      <span
        ><b>Fecha Exp: {{ fechaExpiracion }} </b></span
      >
    </div>
    <footer>
      <span>{{ nombrePropietario }}</span>
      <img :src="tipoTarjeta" width="60" />
    </footer>
  </div>
</template>

<style scoped>
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  background-color: #4158d0;
  background-image: linear-gradient(43deg, #4158d0 0%, #c850c0 46%, #ffcc70 100%);

  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px #c2c2c2;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: sans-serif;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
