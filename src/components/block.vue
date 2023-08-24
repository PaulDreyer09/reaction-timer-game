<template>
  <div class="block" v-if="showBlock">
    Click me!
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return {
            showBlock: false,
        }
    },
    mounted(){
        console.log('mounted');
        setTimeout(() => {
            this.showBlock = true;
            console.log(this.delay)
        }, this.delay);
    },
    updated(){
        console.log('updated');
    },
    unmounted(){
        console.log('unmounted')
    },

}
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        padding: 100px 0;
        margin: 40px auto;
        text-align: center;
        background-color: #0faf87;
        color: #ffffff;
        cursor: pointer;
        
    }
</style>