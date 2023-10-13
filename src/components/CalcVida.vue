<template>
    <div>
        <h1>Calculadora de la Vida</h1>
        <label for="edad">Edad:</label>
        <input type="number" v-model="edad" @input="calcularDinero" maxlength="2">
        <div id="fam">
            <label for="familia">Familia:</label>
            <input type="number" v-model="familia" @input="calcularDinero">
        </div>
        <div id="her">
            <label for="herencia">Herencia Familiar:</label>
            <input type="number" v-model="herencia" @input="calcularDinero">
        </div>
        <div id="gov">
            <label for="gobierno">Gobierno:</label>
            <input type="number" v-model="gobierno" @input="calcularDinero">
        </div>
        <div id="sal">
            <label for="salario">Salario:</label>
            <input type="number" v-model="salario" @input="calcularDinero">
        </div>
        <div id="empre">
            <label for="emprendimiento">Emprendimiento:</label>
            <input type="number" v-model="emprendimiento" @input="calcularDinero">
        </div>
        <div id="par">
            <label for="pareja">Pareja:</label>
            <input type="number" v-model="pareja" @input="calcularDinero">
        </div>
        <div id="hij">
            <label for="hijos">Hijos:</label>
            <input type="number" v-model="hijos" @input="calcularDinero">
        </div>
        <div id="deud">
            <label for="deudas">Deudas:</label>
            <input type="number" v-model="deudas" @input="calcularDinero">
        </div>
        <p>El dinero que tendría a la edad de {{ edad }} es: {{ dinero }}</p>
    </div>
</template>

<script>
export default {
    name: 'CalcVida',
    data() {
        return {
            edad: 0,
            familia: 0,
            herencia: 0,
            gobierno: 0,
            salario: 0,
            emprendimiento: 0,
            pareja: 0,
            hijos: 0,
            deudas: 0,
            dinero: 0
        };
    },
    methods: {
        calcularDinero() {
            if (this.edad > 99) {
                this.edad = 99; // Establece la edad máxima a 99
            }
            this.dinero = (this.familia + this.herencia + this.gobierno + this.salario + this.emprendimiento - this.pareja - this.hijos - this.deudas);
        }
    }
};
</script>