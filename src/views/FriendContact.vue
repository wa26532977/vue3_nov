<template>
    <li>
        <h2>
            {{ name }}
            {{ displayFavorite }}
        </h2>
        <button @click="toggleFavorite">Toggle Favorite</button>
        <button @click="toggleDetails">{{ detailsAreVisible ? "Hide" : "show" }}</button>
        <ul v-if="detailsAreVisible">
            <li>
                <strong>Phone:</strong>
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
        id: {
            type: Number,
            required: true
        },
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
    // emits: ["toggle-favorite"],
    emits: {
        // this for validating of the emit event
        "toggle-favorite": function(id) {
            if (id) {
                return true;
            } else {
                alert("missing id in toggle favorite emits")
                return false;
            }
        }
    },
    data() {
        return {
            detailsAreVisible: false,
        }
    },
    methods: {
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible
        },
        toggleFavorite() {
            // always use cava case
            this.$emit("toggle-favorite", this.id)
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