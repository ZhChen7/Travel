<template>
       <div>
        <detail-banner></detail-banner> 
        <detail-header></detail-header>  
        </div> 
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/header'
export default {
    name:'Detail',
    components:{
        DetailBanner,
        DetailHeader
    }
}
</script>

<style lang="stylus" scoped>

</style>


