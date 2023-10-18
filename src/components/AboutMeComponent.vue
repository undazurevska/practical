<script>
    export default {
        props: ["user"],
    };
</script>

<template>
    <div class="about-me">
        <h1>ABOUT ME</h1>
        <h3>Name: {{ user.name }}</h3>
        <h3>Surname: {{ user.surname }}</h3>
        <h3>Code: {{ user.code }}</h3>
    </div>
</template>

<style>
    .about-me h1 {
        font-size: 30px;
        color: white;
    }

    .about-me h3 {
        font-size: 20px;
        color: white;
        
    }

    .about-me {
        padding: 20px;
    }
</style>
  
