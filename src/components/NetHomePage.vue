<script >
import { RouterLink, RouterView } from 'vue-router'
export default {
    components: {
        name: "allNetLink"
    }
}

</script>













<template>
    <div class="Header0">
        <RouterLink class="customLink" to="/">ホームページ</RouterLink>
        <RouterLink class="customLink" to="/方塊一">方塊一</RouterLink>
        <RouterLink class="customLink" to="/方塊二">方塊二</RouterLink>
        <RouterLink class="customLink" to="/disert">disert</RouterLink>
        <RouterLink class="customLink" to="/Fandi/FandiHome">房地産</RouterLink>
        <RouterLink class="customLink" to="/Expense">記帳</RouterLink>

    </div>
    <div class="Header0">
        <RouterLink class="customLink" to="/components/BOKELAIHeader">博客來網站</RouterLink>
        <RouterLink class="customLink" to="/bikePage/bikeHome">機車網站</RouterLink>
        
        
    </div>
</template>





















<style>
.Header0{
    display: flex;
    justify-content: space-around;
    .customLink{text-decoration: none;
       font-size: 30pt; 
    }
}

</style>