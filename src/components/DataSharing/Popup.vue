<template >
    <div>
        <h3>Data Sharing</h3>
        <h2> show popup</h2>
        <input type="text" v-model="name">
        <button @click="$emit('close',name)">close popup</button>
        
    </div>
</template>
<script>
export default {
    name : 'popup',
    data() {
        return {
            name: ''
        }
    },
    emits : {
        close: (name) =>{
            if(!name){
                return false;
            }
            else return true
        }
    
    },
   message : 'gopi'


    
}
</script>
<style lang="">
    
</style>