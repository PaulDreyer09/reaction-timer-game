<template>
  <p>Reaction time - {{ reactionTime }} ms</p>
  <h3>...{{ showRank() }}</h3>
</template>

<script>
export default {
    props: ['reactionTime'],
    data(){
        return {
            rank: null,
        }
    },
    methods: {
        showRank(){
            if(this.reactionTime < 100){
                this.rank = 'Speedy Gonzalis'
            }else if(this.reactionTime < 250){
                this.rank = 'Sharp Shooter'
            }else if(this.reactionTime < 500){
                this.rank = 'Bumblebee'
            }else if(this.reactionTime < 750){
                this.rank = 'Snail pace'
            }else {
                this.rank = 'Old fossil'
            }
            return this.rank;
        }
    }
}
</script>

<style  scoped>
    h3{
        color: rgb(24, 187, 24);
    }
</style>