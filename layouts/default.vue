<template>
    <v-app>
        <navbar></navbar>
        <slot></slot>

        <custom-footer/>
    </v-app>

</template>

<script>
import Navbar from "../components/layouting/navbar.vue"
import CustomFooter from "../components/layouting/Footer.vue"

export default {
    components: {Navbar, CustomFooter},
    data: () => ({value: 1}),

    computed: {
        color() {
            switch (this.value) {
                case 0:
                    return 'blue-grey'
                case 1:
                    return 'teal'
                case 2:
                    return 'brown'
                case 3:
                    return 'indigo'
                default:
                    return 'blue-grey'
            }
        },
    },
}
</script>


