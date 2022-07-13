<template>
    <div>
        <nav class="container bg-pink-400 md:px-8 p-4 md:py-4 mx-auto md:flex justify-between md:items-center" >
            <div class="flex items-center items-between justify-between">
                <div>
                    <a class="navbar-brand text-white font-bold md:text-4xl" href="#!">
                        E-Saloon Booking
                    </a>
                </div>

                <!-- Mobile menu button -->
                <div class="flex justify-center gap-4">
                    <div @click="showMenu = !showMenu"
                        class="flex md:hidden justify-center gap-4">
                        <button
                        type="button"
                        class="text-gray-800 hover:text-gray-400 focus:outline-none focus:text-gray-400">
                        <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
                            <path
                            fill-rule="evenodd"
                            d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
                            ></path>
                        </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
            <ul :class="showMenu ? 'flex' : 'hidden'"
                class="flex-col mt-8 space-y-2 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
                >
                    <li v-if="!firebaseUser">
                        <NuxtLink
                            class="inline-block px-6 py-2.5 mr-2 bg-gray-200 text-blue-600 font-medium text-xs leading-tight uppercase rounded hover:text-blue-700 hover:bg-gray-100 focus:bg-gray-100 focus:outline-none focus:ring-0 active:bg-gray-200 transition duration-150 ease-in-out"
                            to="/Signin"
                        >
                            Booking
                        </NuxtLink>
                    </li>
                    <li v-if="firebaseUser">
                        <button
                        @click="handleSignout"
                            class="inline-block px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out"
                            
                        >
                            Sign Out
                        </button>
                    </li>
            </ul>
        </nav>

    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>

</style>