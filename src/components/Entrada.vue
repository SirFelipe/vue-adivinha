<template>
    <div class="container">
        <div class="col-md-12">
            <p></p>
            <input type="text" v-model="txtNum" v-on:change="enter"/>
        </div>
    </div>
    
</template>

<script>
export default {
    data(){
       return { txtNum: "" }
    },methods:{
        enter(){
            this.$emit("mudou", this.txtNum);
        }
    }
}
</script>

<style scoped>
    
</style>

