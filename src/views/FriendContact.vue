<template>
    <li>
        <h2>
            {{ name }}
            {{ displayFavorite }}
        </h2>
        <button @click="toggleDetails">{{ detailsAreVisible ? "Hide" : "show" }}</button>
        <ul v-if="detailsAreVisible">
            <li>
                <strong>Phone 123:</strong>
                {{ phoneNumber }}
            </li>
            <li>
                <strong>Email:</strong>
                {{ emailAddress }}
            </li>

        </ul>
    </li>
</template>

<script>
export default {
    name: "FriendContact",
    // props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
    props: {
        name: {
            type: String,
            required: true,
            validator(value) {
                return value.length > 5
            }
        },
        phoneNumber: String,
        emailAddress: String,
        isFavorite: {
            type: Boolean,
            required: false,
            default(rawProps) {
                // console.log(rawProps)
                return rawProps.name === 'peter wang';
            }
        },
    },
    data() {
        return {
            detailsAreVisible: false,
        }
    },
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible
        }
    },
    computed: {
        displayFavorite() {
            // console.log(this.isFavorite)
            if (this.isFavorite) {
                return "(Favorite)"
            }
            return ""
        }
    }
}
</script>

<style scoped>

</style>