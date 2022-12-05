<template>
    <the-navigation />
    <main>
        <router-view />
    </main>
</template>
<script>
import TheNavigation from "@/components/section8/TheNavigation";
export default {
    name: "App",
    components: { TheNavigation },
    data() {
        return {
        }
    },
    methods: {

    }

}
</script>
<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
