<template>
        <div class="popup-overlay">
            <div class="popup-content">
                <center>
                    <svg xmlns="http://www.w3.org/2000/svg" width="80" height="80" fill="#146c43" class="bi bi-check" viewBox="0 0 16 16">
                        <path d="M10.97 4.97a.75.75 0 0 1 1.07 1.05l-3.99 4.99a.75.75 0 0 1-1.08.02L4.324 8.384a.75.75 0 1 1 1.06-1.06l2.094 2.093 3.473-4.425a.267.267 0 0 1 .02-.022z"/>
                    </svg>
                </center>
            <div class="popup-header">
                <center>
                    <h3>ORDINE EFFETTUATO CORRETTAMENTE</h3>
                    <button class="popup-close" @click="this.$root.goPopUp = false,this.$root.goProductList=false,this.$root.goProductsOrder=false,this.$root.goCarrello=false">&times;</button>
                </center>
            </div>
            <div class="popup-body">
                <slot></slot>
            </div>
            </div>
        </div>



</template>


<script>
export default {
  name: 'PopUp',
}

</script>
<style>
.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-content {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
  max-width: 500px;
  max-height: 500px;
  overflow: auto;
}

.popup-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.popup-header h3 {
  margin: 0;
}

.popup-close {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
}

.popup-body {
  max-height: 400px;
  overflow: auto;
}
</style>