<template>
  <div class="d-flex border-end bg-white collapse" id="navbarToggleExternalContent">
        <!-- #region SideBar -->
        <div v-if="this.toggleNavBar == false" class="list col-sm-1 col-md-2 col-lg-2 col-xl-2 col-xxl-2 p-sm-1">
          <div class="sidebar-heading "><img src=""></div>
          <nav class="navbar navbar-light bg-light">
            <button class="navbar-toggler" v-if="this.toggleNavBar == false" @click="this.toggleNavBar = true" type="button" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
          </nav>
          
          <div class="sidebar-heading Title" v-if="toggleNavBar==false">CATEGORIE IN PROMO</div>
          <div class="list-group mt-4 list-group-flush" v-if="toggleNavBar==false">
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">BATTERIE</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">LUBRIFICANTI</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">LPR SAMKO</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">FIAT ALFA LANCIA</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">FORD</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">PEUGEOUT</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">RENAULT</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">NISSAN</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">VOLKSWAGEN</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">Massa Freno</a>
              <a class="list-group-item list-group-item-action list-group-item-light col-sm-2 col-md-2 col-lg-3 col-xl-3 col-xxl-3" href="">EST additivi fluidi</a>
          </div>
        </div>
    <ProductsList v-if="goProductList==false"/>
    <ProductsOrder v-if="goProductsOrder==true"/>
    <ShoppingCart v-if="goCarrello==true"/>
    <Popup v-if="goPopUp==true"/>
    
  </div>
  
</template>

<script>
import './main.js'
import ProductsList from './components/ProductsList.vue' //import ProductsList
import ProductsOrder from './components/ProductsOrder.vue' //import ProductsOrder
import ShoppingCart from './components/ShoppingCart.vue' //Import ShoppingCart
import Popup from './components/PopUp.vue';

export default {
  name: 'App',
  components: {
    ProductsList,
    ProductsOrder,
    ShoppingCart,
    Popup,
  },
  
  data(){
    return{
      goProductsOrder : false,
      goProductList : false,
      goCarrello : false,
      goPopUp : false,
      toggleNavBar : false,
      carrello : [],
      products:[
          {
              name : "BATTERIA",
              id : 0,
              price : 10,
              quantity : 0,
          },
          {
              name : "Other",
              id : 0,
              price : 10,
              quantity : 0,
          },
      ],
    };
  },
  mounted(){


    //Sproducts = 



    if(localStorage.getItem('cart')) {
      // l'array esiste nel local storage, quindi recuperalo e fai qualcosa
      this.carrello = JSON.parse(localStorage.getItem('cart'));
      // fai qualcosa con l'array
    } else {
      // l'array non esiste nel local storage, quindi salva un array vuoto
      localStorage.setItem('cart', JSON.stringify(this.products));
    }
  },
  methods:{
    toggleNavBarF(){
      if(this.toggleNavBar == false){
        this.toggleNavBar = true;
      }
      else{
        this.toggleNavBar = false;
      }
    }
  }
    
}
</script>
