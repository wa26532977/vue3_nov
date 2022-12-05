<template>
    <form action="">
        <div>
            <label for="name">name</label>
            <input id="name" type="text"/>
        </div>
        <div>
            <label for="phone">phone</label>
            <input id="phone" type="tel"/>
        </div>
        <div>
            <label for="email">email</label>
            <input id="email" type="email"/>
        </div>
        <div>
            <button>Add Contact</button>
        </div>
    </form>
</template>

<script>
export default {
    name: "NewFriend",
}
</script>

<style scoped>

</style>