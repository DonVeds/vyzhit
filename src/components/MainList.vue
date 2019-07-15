<template>
  <div>
    <table class="table is-fullwidth">
      <thead>
        <tr>    
          <th>Продукт</th>
        
          <th>Р/Кг</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(product) in products" :key='product.name'>
          <th> {{ product.name }} </th>
          <th> {{ product.price }} </th>
        </tr>
      </tbody>

      <tfoot>
        <tr>
          <th>Продукт</th>
        
          <th>Р/Кг</th>
        </tr>
      </tfoot>
    </table>  
    <div class="field has-addons">
      <div class="control">
        <input class="input inputOfName" v-model="inputOfName" type="text" placeholder="Название">
      </div>
      <div class="control">
        <input class="input inputOfPrice" v-model="inputOfPrice" type="text" placeholder="Цена за кг">
      </div>
      <div class="control">
        <button v-on:click='addItemToList(inputOfName, inputOfPrice, products, saveList)' class="button is-danger">
          Добавить
        </button>
      </div>
    </div>
  </div>
</template>

<script>


// localStorage.setItem('myKey', 'myValue');

// var localValue = localStorage.getItem('myKey');
// console.log(localValue); //"myValue"


export default {
  name: 'MainList',
  data: function() {
    return{
      inputOfName: '',
      inputOfPrice: '',
      products: [],
      number: Number ,
    }
  },
  mounted() {
    if (localStorage.getItem('products')) {
      try {
        this.products = JSON.parse(localStorage.getItem('products'));
      } catch(e) {
        localStorage.removeItem('products')
      }
    } 
  },
  methods: {
    addItemToList: (inputOfName, inputOfPrice, products, saveList) => {
      if (!inputOfName | !inputOfPrice) return

      console.log(inputOfName)
      console.log(inputOfPrice)

      let objToList = {
        "name": inputOfName,
        "price": Number(inputOfPrice)
      }

      console.log(objToList.price)

      function isNumber(n) {
        return !isNaN(parseFloat(n)) && isFinite(n);
      }

      if (!isNumber(objToList.price)) return

      products.push(objToList)

      console.log(products)

      objToList = []
      saveList(objToList)
    },

    removeProduct: (x) => {
      products.slice(x,1)
      saveList()  
    },
    
    saveList: (objToList) => {

      let serialObj = JSON.stringify(objToList)
      
      localStorage.setItem('products', serialObj)
    },
  }
}
</script>

