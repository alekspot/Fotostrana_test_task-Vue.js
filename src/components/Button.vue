<template>
    <button @click="getNewFilms()" class="btn" :disabled="isDisabled">
        <slot></slot>
    </button>
</template>
<script>

export default {
  methods: {
        getNewFilms(){
            this.$store.dispatch('getNewFilms');
        }
  },
  computed:{
        isDisabled(){
            return this.$store.state.isLoading
        }
  }
}
</script>
<style lang="scss">
   .btn {
       display: block;
       margin: 35px auto ;
       background: #108CE5;
       color:#fff;
       font-size: 13px;
       font-family: Tahoma;
       padding: 8px 44px;
       border-radius: 4px;
       outline: none;
       border: none;
       cursor: pointer;
   }
</style>
