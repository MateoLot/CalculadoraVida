<template>
  <div>
    <h1>Calculadora de la Vida</h1>
    <div>
      <label for="edad">Edad:</label>
      <input type="number" v-model="edad" @input="calcularDinero">
    </div>

    <div v-if="edad >= 0 && edad <= 17">
      <h2>Preguntas para menores de edad</h2>
      <div class="input-gr">
      <label for="mesada">Mesada:</label>
      <input type="number" v-model="mesada" @input="calcularDinero">
      <label for="regalos">Regalos:</label>
      <input type="number" v-model="regalos" @input="calcularDinero">
      <label for="herencias">Herencias:</label>
      <input type="number" v-model="herencias" @input="calcularDinero">
      </div>
    </div>

    <div v-else-if="edad >= 18 && edad <= 40">
      <h2>Preguntas para adultos jóvenes</h2>
      <div class="input-gr">
      <label for="familia">Familia:</label>
      <input type="number" v-model="familia" @input="calcularDinero">
      <label for="regalos">Regalos:</label>
      <input type="number" v-model="regalos" @input="calcularDinero">
      <label for="herencias">Herencias:</label>
      <input type="number" v-model="herencias" @input="calcularDinero">
      <label for="salario">Salario:</label>
      <input type="number" v-model="salario" @input="calcularDinero">
      <label for="hijos">Hijos:</label>
      <input type="number" v-model="hijos" @input="calcularDinero">
      <label for="pareja">Pareja:</label>
      <input type="number" v-model="pareja" @input="calcularDinero">
      <label for="deudas">Deudas:</label>
      <input type="number" v-model="deudas" @input="calcularDinero">
      </div>
    </div>

    <div v-else>
      <h2>Preguntas para adultos mayores</h2>
      <div class="input-gr">
      <label for="herencia">Herencia:</label>
      <input type="number" v-model="herencia" @input="calcularDinero">
      <label for="sueldo">Sueldo:</label>
      <input type="number" v-model="sueldo" @input="calcularDinero">
      <label for="subsidios">Subsidios/Jubilación:</label>
      <input type="number" v-model="subsidios" @input="calcularDinero">
      <label for="salario">Salario:</label>
      <input type="number" v-model="salario" @input="calcularDinero">
      <label for="pareja">Pareja:</label>
      <input type="number" v-model="pareja" @input="calcularDinero">
      <label for="hijos">Hijos:</label>
      <input type="number" v-model="hijos" @input="calcularDinero">
      <label for="deudas">Deudas:</label>
      <input type="number" v-model="deudas" @input="calcularDinero">
      </div>
    </div>

    <p>El dinero que tendría acumulado a la edad de {{ edad }} es: {{ dinero }}</p>
  </div>
</template>

<script>
export default {
  name: 'CalcVida',
  data() {
    return {
      edad: 0,
      mesada: 0,
      regalos: 0,
      herencias: 0,
      familia: 0,
      salario: 0,
      hijos: 0,
      pareja: 0,
      deudas: 0,
      herencia: 0,
      sueldo: 0,
      subsidios: 0,
      dinero: 0
    };
  },
  methods: {
    calcularDinero() {
      if (this.edad > 99) {
      this.edad = 99; 
    }  
      if (this.edad >= 0 && this.edad <= 17) {
        this.dinero = this.mesada + this.regalos + this.herencias;
      } else if (this.edad >= 18 && this.edad <= 40) {
        this.dinero = this.familia + this.regalos + this.herencias + this.salario - this.hijos - this.pareja - this.deudas;
      } else {
        this.dinero = this.herencia + this.sueldo + this.subsidios + this.salario - this.pareja - this.hijos - this.deudas;
      }
    }
  }
};
</script>