<template>
  <div>
    <table class="table is-fullwidth">
      <thead>
        <tr>
          <th>№</th>
        
          <th>Продукт</th>
        
          <th>Р/Кг</th>
        </tr>
      </thead>

      <tbody>
        <tr>
        </tr>
      </tbody>

      <tfoot>
        <tr>
          <th>№</th>
        
          <th>Продукт</th>
        
          <th>Р/Кг</th>
        </tr>
      </tfoot>
    </table>  
    <!-- TODO: Try v-modal on inputs -->
    <div class="field has-addons">
      <div class="control">
        <input class="input inputOfName" type="text" placeholder="Название">
      </div>
      <div class="control">
        <input class="input inputOfPrice" type="text" placeholder="Цена за кг">
      </div>
      <div class="control">
        <button v-on:click='addItemToList' class="button is-danger">
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
  data() {
    return {
      couner: 0,
    }
  },
  methods: {
    addItemToLIst: function(event) {
      let Name = document.querySelector('inputOfName')
      let Price = document.querySelector('inputOfPrice')

      this.couner++
      localStorage.setItem(this.couner, [Name, Price])
    }
  }
}
console.log(localStorage);
</script>

