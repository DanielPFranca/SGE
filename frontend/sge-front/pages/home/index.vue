<script setup lang="ts">

const { signOut } = useAuth();

definePageMeta({
    middleware: 'auth'
})

const submitLogout = () => {

    signOut({redirect: false}).then(()=>{

        console.log("Successfully logout!")
        navigateTo('/');
    })
        .catch((error)=>{
        console.log("Error when trying to logout: ", error);
    }); 

}
</script>


<template>

<div>
    <h1>Minha tela Home</h1>
    
    <button type="submit" @click="submitLogout" class="customButton">Sair</button>
</div>

</template>

<style >


</style>