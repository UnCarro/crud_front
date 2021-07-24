<template>
    <header>
        <b-navbar type="dark" variant="dark">
           <b-navbar-nav class="ml-auto">
               <b-navbar-brand href="/"> {{ title }} </b-navbar-brand> 
            </b-navbar-nav>
        </b-navbar>   
    </header>
</template>

<script>
export default{
    name: 'Header',
    props: {
        title:{
            required: true,
            type: String,

        }, 
       
    }
}
</script>
<style scoped>
a{
   color: white;
}

</style>