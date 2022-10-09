<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
</script>

<template>
    <Head title="Welcome" />

    <div class="relative flex items-top justify-center min-h-screen bg-gradient-to-br from-violet-900 to-green-600">

        <div class="m-5 p-5">
            <div v-if="canLogin" class="hidden p-5 sm:block">
                <Link v-if="$page.props.user" :href="route('dashboard')" class="text-sm text-gray-700 dark:text-gray-500 underline">Dashboard</Link>

                <template v-else>
                    <Link :href="route('login')" class="text-md text-white underline">Log in</Link>

                    <Link v-if="canRegister" :href="route('register')" class="ml-4 text-md text-white underline">Register</Link>
                </template>
            </div>
            <div class="mt-5 mb-5 p-5 bg-black/20 overflow-hidden shadow sm:rounded-lg">
                <div class="text-6xl text-white">
                    Welcome to your Jetstream application!
                </div>

                <div class="mt-6 text-white text-2xl">
                    Laravel Jetstream provides a beautiful, robust starting point for your next Laravel application. Laravel is designed
                    to help you build your application using a development environment that is simple, powerful, and enjoyable. We
                    believe you should love expressing your creativity through programming, so we have spent time carefully crafting
                    the Laravel ecosystem to be a breath of fresh air. We hope you love it.
                </div>
            </div>

            <div class="flex justify-center mt-4 p-5 sm:items-center sm:justify-between">
                <div class="text-center text-sm text-gray-500 sm:text-left">
                    <div class="flex items-center">
                        <svg
                            fill="none"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                            class="-mt-px w-5 h-5 text-white"
                        >
                            <path d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
                        </svg>

                        <a href="https://laravel.bigcartel.com" class="ml-1 text-white underline">
                            Shop
                        </a>

                        <svg
                            fill="none"
                            stroke="currentColor"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            viewBox="0 0 24 24"
                            class="ml-4 -mt-px w-5 h-5 text-white"
                        >
                            <path d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
                        </svg>

                        <a href="https://github.com/sponsors/taylorotwell" class="ml-1 text-white underline">
                            Sponsor
                        </a>
                    </div>
                </div>

                <div class="ml-4 text-center text-sm text-gray-500 sm:text-right sm:ml-0">
                    Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
                </div>
            </div>
        </div>
    </div>
</template>
