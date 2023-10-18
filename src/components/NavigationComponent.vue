<script>
    export default {
        props: ["activeTab"],
        methods: {
            navigate(tab) {
                this.$emit("navigate", tab);
            },
        },
    };
</script>

<template>
    <nav class="navigation">
            <button @click="navigate('home')" :class="{ active: activeTab === 'home' }"> HOME </button>  
            <button @click="navigate('about')" :class="{ active: activeTab === 'about' }"> ABOUT ME </button>
    </nav>
</template>

<style>
.navigation {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
  gap: 10px;

}

.navigation button {
  background-color: #7448E0;
  color: white;
  width: 80%;
  padding: 15px;
  border: none;
  border-radius: 0 0 5px 5px;
  cursor: pointer;
  transition: background-color 0.2s;
  transform: skewX(-20deg) top left;
  border-radius: 0;
  text-align: left;

}

.navigation button.active {
  background-color: #191621;
}

</style>