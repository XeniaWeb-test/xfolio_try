<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
})
</script>

<template>
    <Head title="Welcome" />

    <div class="relative flex items-top justify-center min-h-screen bg-gray-100 dark:bg-gray-900 items-start  xl:items-center sm:pt-0 bg-hero-bg">
        <div v-if="canLogin" class="hidden fixed top-0 right-0 px-6 py-4 sm:block space-x-3">
            <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="text-sm text-stone-500 hover:text-stone-400 active:text-stone-300 underline pr-2">
                Dashboard
            </Link>
            <Link v-if="$page.props.auth.user" :href="route('about')" class="text-sm text-stone-500 hover:text-stone-400 active:text-stone-300 underline pr-2">
                About
            </Link>
            <Link v-if="$page.props.auth.user" :href="route('contacts')" class="text-sm text-stone-500 hover:text-stone-400 active:text-stone-300 underline pr-2">
                Contacts
            </Link>

            <template v-else>
                <Link :href="route('login')" class="text-sm text-stone-400 hover:text-stone-300 underline pr-2">
                    Log in
                </Link>

                <Link v-if="canRegister" :href="route('register')" class="text-sm text-stone-400 hover:text-stone-300 underline pr-2">
                    Register
                </Link>
            </template>
        </div>
        <h1 class="my-14 p-5 text-[burlywood] xl:text-right text-left rounded-xl text-2xl mr-[5%] ml-auto backdrop-blur backdrop-opacity-60">
            Great site by <strong>XeniaWeb</strong> will be here soon  <br> <br>xenia1898@gmail.com
        </h1>

    </div>
</template>

<style scoped>
    .bg-gray-100 {
        background-color: #f7fafc;
        background-color: rgba(247, 250, 252, var(--tw-bg-opacity));
    }

    .border-gray-200 {
        border-color: #edf2f7;
        border-color: rgba(237, 242, 247, var(--tw-border-opacity));
    }

    .text-gray-400 {
        color: #cbd5e0;
        color: rgba(203, 213, 224, var(--tw-text-opacity));
    }

    .text-gray-500 {
        color: #a0aec0;
        color: rgba(160, 174, 192, var(--tw-text-opacity));
    }

    .text-gray-600 {
        color: #718096;
        color: rgba(113, 128, 150, var(--tw-text-opacity));
    }

    .text-gray-700 {
        color: #4a5568;
        color: rgba(74, 85, 104, var(--tw-text-opacity));
    }

    .text-gray-900 {
        color: #1a202c;
        color: rgba(26, 32, 44, var(--tw-text-opacity));
    }

    @media (prefers-color-scheme: dark) {
        .dark\:bg-gray-800 {
            background-color: #2d3748;
            background-color: rgba(45, 55, 72, var(--tw-bg-opacity));
        }

        .dark\:bg-gray-900 {
            background-color: #1a202c;
            background-color: rgba(26, 32, 44, var(--tw-bg-opacity));
        }

        .dark\:border-gray-700 {
            border-color: #4a5568;
            border-color: rgba(74, 85, 104, var(--tw-border-opacity));
        }

        .dark\:text-white {
            color: #fff;
            color: rgba(255, 255, 255, var(--tw-text-opacity));
        }

        .dark\:text-gray-400 {
            color: #cbd5e0;
            color: rgba(203, 213, 224, var(--tw-text-opacity));
        }
    }
</style>
