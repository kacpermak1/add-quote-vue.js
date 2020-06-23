<template>
<div class="alert alert-primary" role="alert">
  {{ message() }}
</div>
</template>

<script>
export default {
    data: function(){
        return{
        }
    },

    props:{
        quotesNumber: Number
    },

    methods:{
        message(){
            if(!this.quotesNumber){
               return 'Info: You have not added any quotes yet! Write your first quote and click the button above.'
            }else if(this.quotesNumber && this.quotesNumber < 10){
                return 'Info: Click on the quote to delete it!'
            }else{
                return 'Info: You have reached maximum number of quotes. Click on the quote to delete it!'
            }
        }
    }
}
</script>

<style lang="scss" scoped>

</style>