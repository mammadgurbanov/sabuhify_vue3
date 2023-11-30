<template>
    <v-container>
        <v-sheet>
            <div class="m-homepage">
                <v-row>
                    <v-col cols="12" md="8">
                        <div class="m-homepage__left">
                            <h1 class="m-homepage__left--title">{{ heading }}</h1>
                            <p class="m-homepage__left--description">{{ desc }}</p>
                            <v-sheet width="400">
                                <packs-view/>
                            </v-sheet>
                        </div>
                    </v-col>
                    <v-col cols="12" md="4">
                        <div class="m-homepage__right">
                            <v-sheet
                                    :elevation="3"
                                    border
                                    class="w-100 p-4"
                                    rounded
                            >
                                <RegistrationForm/>
                            </v-sheet>

                        </div>
                    </v-col>
                </v-row>
            </div>
        </v-sheet>
    </v-container>
</template>

<script>
import RegistrationForm from "../components/forms/registration.vue"
import PacksView from "../components/views/packs.vue"

export default {
    components: {RegistrationForm, PacksView},
    data() {
        return {
            heading: "We are great like Səbuhi Əlizadə",
            desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.",
        }
    }
}
</script>

<style lang="scss">
.m-homepage {
  padding-top: 100px;

  &__right {
    margin-top: 24px;
  }
}
</style>
