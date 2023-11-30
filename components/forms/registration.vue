<template>
    <form class="m-2">
        <div class="px-4 py-4">
            <h2 class="mb-2">Register now</h2>

            <v-text-field
                    variant="solo"
                    clearable
                    v-model="state.name"
                    :counter="10"
                    :error-messages="v$.name.$errors.map(e => e.$message)"
                    label="Name"
                    required
                    @blur="v$.name.$touch"
                    @input="v$.name.$touch"
            ></v-text-field>

            <v-text-field
                    variant="solo"
                    clearable
                    v-model="state.email"
                    :error-messages="v$.email.$errors.map(e => e.$message)"
                    label="E-mail"
                    required
                    @blur="v$.email.$touch"
                    @input="v$.email.$touch"
            ></v-text-field>

            <v-select
                    variant="solo"
                    clearable
                    v-model="state.select"
                    :error-messages="v$.select.$errors.map(e => e.$message)"
                    :items="items"
                    label="Item"
                    required
                    @blur="v$.select.$touch"
                    @change="v$.select.$touch"
            ></v-select>

            <v-checkbox
                    v-model="state.checkbox"
                    :error-messages="v$.checkbox.$errors.map(e => e.$message)"
                    label="Do you agree?"
                    required
                    @blur="v$.checkbox.$touch"
                    @change="v$.checkbox.$touch"
            ></v-checkbox>

            <v-btn
                    class="mx-1"
                    color="#5865f2"
                    prepend-icon="mdi-test-tube"
                    variant="flat"
                    @click="v$.$validate"
            >
                submit
            </v-btn>
            <v-btn
                    class="mx-1"
                    color="#5865f2"
                    prepend-icon="mdi-test-tube"
                    variant="flat"
                    @click="clear">
                clear
            </v-btn>
        </div>
    </form>

</template>

<script setup>
import {reactive} from 'vue'
import {useVuelidate} from '@vuelidate/core'
import {email, required} from '@vuelidate/validators'

const initialState = {
    name: '',
    email: '',
    select: null,
    checkbox: null,
}

const state = reactive({
    ...initialState,
})

const items = [
    'Item 1',
    'Item 2',
    'Item 3',
    'Item 4',
]

const rules = {
    name: {required},
    email: {required, email},
    select: {required},
    items: {required},
    checkbox: {required},
}

const v$ = useVuelidate(rules, state)

function clear() {
    v$.value.$reset()

    for (const [key, value] of Object.entries(initialState)) {
        state[key] = value
    }
}
</script>
