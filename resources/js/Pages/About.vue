<script setup>
import AppLogoXeniaWeb from '@/Components/AppLogoXeniaWeb.vue';
import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue';
import { Head, Link } from '@inertiajs/inertia-vue3';
// import { Link } from '@inertiajs/inertia-vue3';
</script>

<template>
    <Head title="About" ></Head>

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                About me
            </h2>
        </template>

        <div class="sm:py-4 xl:py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="sm:flex  bg-white overflow-hidden shadow-sm sm:rounded-lg">
                        <img src="../../assets/images/1.jpg" alt="Photo" class="w-full sm:w-1/2 xl:w-1/3 lg:w-1/4">
                    <div class="p-6 bg-white border-b border-gray-200">
                        About - text new
                    </div>
                </div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>
