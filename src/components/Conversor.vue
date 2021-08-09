<template>
<div class="init">
    <div class="element">
        <h3 class="dePara"> {{moedaA}} to {{moedaB}} </h3>
        <input type="number" v-bind:placeholder="moedaA" v-model="moedaA_value">
        <button @click="converter">Enviar</button>
        <h2> {{ moedaB_value }} </h2>
    </div>
</div>
</template>

<script>

export default {
    name: "Init",
    data: function (){
        return {
            moedaA_value: '',
            moedaB_value: ''
        }
    },
    props: [
        'moedaA', 'moedaB'
    ],
    methods: {
        converter: function(){

            let de_para = this.moedaA + "_" + this.moedaB

            let url = `https://free.currencyconverterapi.com/api/v5/convert?q=${de_para}&compact=ultra&apiKey=cb2af04e87a529b9e1dd`

            fetch(url)
                .then(res=>{
                    return res.json()
                })
                .then(json=>{
                    //let cotacao = json[de_para].val
                    console.log(json[de_para])

                    this.moedaB_value = parseInt(json[de_para] * parseFloat(this.moedaA_value)).toFixed(2)
                })
        }
    }
    
}
</script>

<style scoped>
    .element {
        width: 35vw;
        height: 35vh;
        margin: 0 auto;
        padding: 1rem 0;
        border-radius:15px;
        background-color: #bec4a4;
    }
    input, button {
        margin: 0 0.2rem;
        padding: 0.5rem;
        border: none;

    }
</style>