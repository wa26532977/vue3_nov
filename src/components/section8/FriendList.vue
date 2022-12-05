<template>
    <ul>
        <friend-contact
            v-for="friend in friends"
            :key="friend.id"
            :id="friend.id"
            :name="friend.name"
            :phone-number="friend.phone"
            :email-address="friend.email"
            :is-favorite="friend.favorite"
            @toggle-favorite="toggleFavorite"
        ></friend-contact>
        <!--        <friend-contact name="Manuel Lorenz" phone-number="2012135" email-address="jlkajsdf@gmail.com" :is-favorite='true'></friend-contact>-->
        <!--        <friend-contact name="peter wang" phone-number="12012135" email-address="aaaakajsdf@gmail.com"></friend-contact>-->
    </ul>
</template>

<script>
import FriendContact from "@/views/FriendContact";

export default {
    name: "FriendList",
    components: {FriendContact},
    data() {
        return {
            friends: [
                {
                    id: 1,
                    name: "Manuel",
                    phone: "505213613131",
                    email: "dsfasdf@gmail.com",
                    favorite: true
                },
                {
                    id: 2,
                    name: "1Manuel",
                    phone: "1505213613131",
                    email: "1dsfasdf@gmail.com",
                    favorite: false
                }
            ]
        }
    },
    methods: {
        toggleFavorite(friendId) {
            console.log("toggle Favorite: " +  friendId)
            const identifiedFriend = this.friends.find(friend => friend.id === friendId)
            identifiedFriend.favorite = !identifiedFriend.favorite
            console.log(identifiedFriend)
        }
    }
}
</script>

<style scoped>

</style>