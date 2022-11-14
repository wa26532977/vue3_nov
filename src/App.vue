<template>
    <!--  <nav>-->
    <!--    <router-link to="/">Home</router-link> |-->
    <!--    <router-link to="/about">About</router-link>-->
    <!--  </nav>-->

    <header>
        <h1>My Friends</h1>
    </header>
    <ul>
        <friend-contact
            v-for="friend in friends"
            :key="friend.id"
            :name="friend.name"
            :phone-number="friend.phone"
            :email-address="friend.email"
            :is-favorite="friend.favorite"

        ></friend-contact>
<!--        <friend-contact name="Manuel Lorenz" phone-number="2012135" email-address="jlkajsdf@gmail.com" :is-favorite='true'></friend-contact>-->
<!--        <friend-contact name="peter wang" phone-number="12012135" email-address="aaaakajsdf@gmail.com"></friend-contact>-->
    </ul>
</template>
<script>
import FriendContact from "@/views/FriendContact";

export default {
    name: "App",
    components: {FriendContact},
    data () {
        return {
            friends: [
                {
                    name: "Manuel",
                    phone: "505213613131",
                    email: "dsfasdf@gmail.com",
                    favorite: true
                },
                {
                    name: "1Manuel",
                    phone: "1505213613131",
                    email: "1dsfasdf@gmail.com"
                }
            ]
        }
    }

}
</script>
<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

nav {
    padding: 30px;
}

nav a {
    font-weight: bold;
    color: #2c3e50;
}

nav a.router-link-exact-active {
    color: #42b983;
}
</style>
