<template>
    <div class="alert " :class="type">
        <p class="alert-title">{{ title }}</p>
        <p>{{ text }}</p>
        <button class="btn" :class="type" v-if="closable" @click="$emit('close',)">Закрыть</button>
    </div>

</template>

<script>
export default{
    emits:['close'],
    props:{
        text:String,
        title:String,
        closable:{
            type:Boolean,
            reqired:false,
            default:false
        },
        type:{
            type:String,
            default:'primary',
            validator(val){
                return['primary','danger','warning'].includes(val)
            }
        }
    }
}
</script>

<style scoped>

</style>