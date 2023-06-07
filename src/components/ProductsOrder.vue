<template>

<div class="row ml-5">
    <div class="row-sm-3 row-md-3 row-lg-3 row-xxl-4 my-2">
        <div class="Title"><h1>PROMOLIST - <b>BATTERIE</b></h1></div>
    </div>
    <center>
    <div class = "col-sm-3 col-md-3 col-lg-3 " id="carrello">
        <div class="amount">
            <h4>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart-fill" viewBox="0 0 16 16">
                    <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
                </svg>
                $ {{ this.total }}
            </h4>
        </div>
    </div>
    </center>
    <div class="row mx-1 justify-content-center">
        <table class="table table ml-3">
            <thead>
                <tr>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Head</th>
                <th scope="col">Nome</th>
                <th scope="col">Quantità</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(items) in this.$root.carrello" :key="items.id">
                    <th scope="row text-center">{{ items.id }}</th>
                    <td>1</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>Cell</td>
                    <td>{{ items.name }}</td>
                    <td><button class="btn btn-transparent" @click="addQuantity(-1,items.name)">-</button> {{ items.quantity }} <button class="btn btn-transparent" @click="addQuantity(1,items.name)">+</button></td>
                </tr>
            </tbody>
        </table>
    </div>
    <br>
    <center>
        <button class="btn btn-success changeSize" @click="this.$root.goProductsOrder = false,this.$root.goCarrello = true">VAI AL CARRELLO ${{ this.total }} </button>
    </center>
</div>
</template>




<script>




export default {
  name: 'ProductsOrder',
  data(){
    return{
        total : 0,
        
    }
  },
  mounted(){
    this.calculateTotal();
  },
  methods:{
    addQuantity(val,objectToAdd){
        //Find Object
        
        let slot = 0;
        for(let i=0;i<this.$root.carrello.length;i++){
            if(objectToAdd==this.$root.carrello[i].name){
                slot = i;
            }
        }
        console.log(slot);
        console.log(objectToAdd);
        //Check if is adding or no
        if(val==1){
            this.$root.carrello[slot].quantityProduct+=1;
            this.$root.carrello[slot].quantity++;
            localStorage.setItem('cart', JSON.stringify(this.$root.carrello));
            this.calculateTotal();
        }
        if(val==-1){
            if(this.$root.carrello[slot].quantity!=0){
                this.$root.carrello[slot].quantity--;
                localStorage.setItem('cart', JSON.stringify(this.$root.carrello));
            }
            this.calculateTotal();
        }
    },
    calculateTotal(){
        this.total = 0;
        for(let i=0;i<this.$root.carrello.length;i++){
            if(this.$root.carrello[i].quantity != 0){
                this.total += this.$root.carrello[i].quantity * this.$root.carrello[i].price;
            }
        }
    },
  }

}
</script>