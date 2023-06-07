<template>

<div class="row ml-5">
    <div class="row-sm-3 row-md-3 row-lg-3 row-xxl-4 mx-4 my-2">
        <div class="Title"><h1>PROMOLIST - PRODUCTS</h1></div>
    </div>

    <div class="row-sm-3 row-md-3 row-lg-3 row-xxl-4 mx-4" v-if="this.$root.carrello.length >= 1">
        <div class="title">NOME CATEGORIA</div>
    </div>
    <div class="row my-3 mx-4" v-if="this.$root.carrello.length == 0">
        <h1 class="title">IL CARRELLO è VUOTO</h1>
    </div>
    <div class="row" v-if="this.$root.carrello.length >= 1">
        <table class="table table col-sm-12 col-md-4 mx-5" v-for="(items) in this.$root.carrello" :key="items.name">
            
                <thead v-if="items.quantity>0">
                    <tr>
                    <th scope="col">Head</th>
                    <th scope="col">Head</th>
                    <th scope="col">Head</th>
                    <th scope="col">Head</th>
                    <th scope="col">Head</th>
                    <th scope="col">Head</th>
                    <th scope="col">Nome Prodotto</th>
                    <th scope="col">Head</th>
                    <th scope="col">Quantità</th>
                    </tr>
                </thead>
                <tbody v-if="items.quantity>0">
                    <tr>
                    <th scope="row">1</th>
                    <td>1</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>{{ items.name }}</td>
                    <td></td>
                    <td>{{ items.quantity }}</td>
                    </tr>
                </tbody>
        </table>
        <div class="buy" v-if="this.$root.carrello.length >= 1">
            <br>
            <label>Imponibile $ {{ calculateImponibile() }}</label>
            <br>
            <label>Iva $ {{ calculateIva() }} </label>
            <br>
            <label>Total $ {{ calculateTotal() }}</label>
            <br>
            <button type="button" class="btn btn-success" @click="this.$root.goPopUp = true">Click to buy</button>
        </div>
    </div>
</div>

</template>



<script>



export default {
    name: 'ShoppingCart',


    data(){
        return{
            imponibile : 0,
            iva : 0,
            total : 0,
        }
    },

    methods:{
        calculateImponibile(){
            this.imponibile = 0;
            for (let i=0;i<this.$root.carrello.length;i++){
                    this.imponibile += this.$root.carrello[i].price*this.$root.carrello[i].quantity;
            }
            return this.imponibile;
        },
        calculateIva(){
            this.iva = parseInt(this.total/100*22);
            return this.iva;
        },
        calculateTotal(){
            this.total = parseInt(this.imponibile + this.iva);
            return this.total;
        }
    }
}
</script>
