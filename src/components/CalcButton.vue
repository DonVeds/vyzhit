<template>
  <div>
    <a v-on:click='openModal' class="button calcButton is-large is-danger">
      <span class="icon is-medium">
        <font-awesome-icon icon="calculator" />
      </span>
    </a>

    <div class="modal modalBlock">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Modal title</p>
          <button v-on:click='closeModal' class="delete" aria-label="close"></button>
        </header>
        <section class="modal-card-body">
          <!-- Content ... -->
          <p>ты пидор</p>
        </section>
        <footer class="modal-card-foot">
          <button class="button is-danger">Копировать</button>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalcButton',
  methods: {
    openModal: function () {
      document.querySelector('.modalBlock').classList.add('is-active')
    },
    closeModal: function () { 
      document.querySelector('.modalBlock').classList.remove('is-active')
    }
  }
}
</script>

<style lang="sass">
.calcButton
  position: absolute !important
  bottom: 25px
  right: 25px
</style>

