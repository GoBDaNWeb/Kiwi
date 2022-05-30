<template>
    <div class="w-full min-h-screen flex items-center justify-center">
        <div class="bg-gray-100 p-6 shadow-lg rounded-lg min-w-[340px] text-lg">
            <h2 class="text-2xl font-bold text-center my-2">
                Forgot Password?
            </h2>
            <form class="my-4" @submit.prevent="handleRestore">

                <label class="block relative mb-3">
                    <i class="fas fa-envelope absolute top-[15px] left-3 text-coolGray-400 z-50"></i>
                    <input 
                        type="email"
                        required
                        placeholder="Your E-Mail"
                        v-model="email"
                        class="relative z-10 p-2 pl-10 block rounded-md transition border-2 border-blueGray-300 focus:outline-none focus:border-blueGray-400"
                    >
                </label>
                <hr class="my-4">
                <div class="flex justify-center items-center">
                    <button class="py-2 px-4 rounded-md bg-blue-500 text-white transition hover:bg-blue-600" type="submit">
                        <i class="fas fa-user-lock mr-1"></i>
                        Restore
                    </button>
                </div>
                <hr class="my-4">
                <div class="flex justify-between items-center text-base">
                    <router-link to="/register">
                        Create an account
                    </router-link>
                    <router-link to="/login">
                        I have a password
                    </router-link>
                </div>
                <Alert :message="error" type="error" v-if="error" />

            </form>
        </div>
    </div>
</template>

<script>
import { ref } from "@vue/reactivity"
import Alert from "../components/Alert.vue"

export default {
    setup() {
        const email = ref('')
        const error = ref("")

        const handleRestore = () => {
            console.log(email.value);
        }

        return {email, error, handleRestore}
    },
    components: { Alert }
}
</script>