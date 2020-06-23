<template>
<div>
<h3>Quote</h3>
  <div class="input-group">
    <div class="input-group-prepend">
    </div>
    <textarea class="form-control" aria-label="Quote" v-model="textToAdd"></textarea>
    <button @click="handleAddQuote()" type="button" class="btn btn-dark btn-lg btn-block">Add Quote</button>
  </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            textToAdd:''
        }
    },

    props:{
        addQuote: Function,
        quotesNumber: Number
    },

    methods:{
        handleAddQuote(){
            if(this.textToAdd.trim() !== "" && this.quotesNumber<10){
            this.addQuote(this.textToAdd);
            this.textToAdd = '';
            }
        }
    }
}
</script>

<style lang="scss" scoped>
textarea{
    resize: none;
    height: 260px;
}
</style>
