<template>
  
  <div class="page-content-wrapper my-4 mx-2">
    <nav class="navbar navbar-light bg-light">
      <button class="navbar-toggler" v-if="this.$root.toggleNavBar == true" @click="this.$root.toggleNavBar = false" type="button" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
    </nav>
    <div class="row">
      <div class="row-sm-3 row-md-3 row-lg-3 row-xxl-4">
        <h1 class="Title">PROMOLIST</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-6 col-md-3 col-lg3 shadowCard">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Batterie</h5>
            <img class="img-fluid batteria" src="../assets/batteria.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class = "col-sm-4 col-md-3 col-lg-3" id="carrello">
                <div class="amount">
                  <h4>
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart-fill" viewBox="0 0 16 16">
                      <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
                    </svg>
                    $ {{ calculateImponibile() }}
                  </h4>
                </div>
                <div class="card-customer text-center">
                    <center>
                    <h5 class="card-title TitleMarchi text-center">I MARCHI</h5>
                    </center>
                    <div class="row1 d-flex text-center">
                          <img class="MarchiImg" src="../assets/iveco.png" style="max-width: 80%;" alt="Iveco">
                          <img class="MarchiImg" src="../assets/Jeep.png" style="max-width: 60%;" alt="Jeep">
                        </div>
                        <div class="row2 d-flex text-center">
                          <img class="MarchiImg" src="../assets/toyota.png" style="max-width: 70%;" alt="Toyota">
                          <img class="MarchiImg" src="../assets/Lancia.png" style="max-width: 80%;" alt="Lancia">
                          <img class="MarchiImg" src="../assets/peugeot.png" style="max-width: 60%;" alt="Peugeot">
                        </div>
                </div>
              </div>
      </div>
  
  <div class="row">
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Batterie</h5>
            <img class="img-fluid batteria" src="../assets/batteria.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
  </div>
  <div class="row">
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Batterie</h5>
            <img class="img-fluid batteria" src="../assets/batteria.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
      <div class="col-sm-6 col-md-3 col-lg-3">
        <div class="card">
          <div class="card-body text-center">
            <h5 class="card-title">Lubrificanti</h5>
            <img class="img-fluid lubrificante" src="../assets/lubrificante.jpg"/>
            <br>
            <button @click="this.$root.goProductList = !$goProductList, this.$root.goProductsOrder = true" class="btn btn-primary stretched-link bg-success">Compra</button>
          </div>
        </div>
      </div>
  </div>
</div>
</template>

<script>


export default {
  name: 'ProductsList',
  
  methods:{
    calculateImponibile(){
      let imponibile = 0;
      for(let i=0;i<this.$root.carrello.length;i++){
        if(this.$root.carrello[i].quantity != 0){
          imponibile += this.$root.carrello[i].quantity * this.$root.carrello[i].price;
        }
      }
      return imponibile;
    }
  }
  
}
</script>
