<template>
    <form action="">
        <div>
            <label for="name">name</label>
            <input id="name" type="text" v-model="newFriend.name"/>
        </div>
        <div>
            <label for="phone">phone</label>
            <input id="phone" type="tel" v-model="newFriend.phone"/>
        </div>
        <div>
            <label for="email">email</label>
            <input id="email" type="email" v-model="newFriend.email"/>
        </div>
        <div>
            <button @click="addNewContact">Add Contact</button>
        </div>
    </form>
</template>

<script>
export default {
    name: "NewFriend",
    emits: ['add-contact'],
    data() {
      return {
          newFriend: {
              name: "",
              phone: "",
              email: ""
          }
      }
    },
    methods: {
        addNewContact() {
            this.$router.push('/')
        }
    }
}
</script>

<style scoped>

</style>