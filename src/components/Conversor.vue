<template>
    <div class="conversor">
        <h2>{{moedaA}} para {{moedaB}} </h2>
        <input type="text" v-model="mA_valor" placeholder="Insira um valor">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{mB_valor}}</h2>

    </div>
</template>

<script>
export default {
    name: "ConversorM",
    props: ["moedaA","moedaB"],
        data(){
            return{
                mA_valor : "",
                mB_valor : 0
            };
        },
        methods: {
            converter(){
                let de_para = this.moedaA + "_"+this.moedaB;

                let url = "https://free.currconv.com/api/v7/convert?q="+de_para+"&compact=ultra&apiKey=d4b5491bae6308c6c988"

            fetch(url).then(res=>{return res.json()})
                .then(json=>{
                    
                    let cotacao = json[de_para];
                    this.mB_valor = (cotacao * parseFloat(this.mA_valor)).toFixed(2);
                });

           
           
           }
        }
};
</script>

<style scoped>

    .conversor{
        padding: 20px;
        max-width: 300px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    }
</style>

