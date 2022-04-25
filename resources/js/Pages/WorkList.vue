<script setup>
import XenBaseLayout from '@/Layouts/Base.vue';
import { Head, Link } from '@inertiajs/inertia-vue3';

defineProps({

});
</script>

<template>
    <Head title="Works" />

    <XenBaseLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                List of Works
            </h2>
        </template>

        <div class="sm:py-4 xl:py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="sm:flex  bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        What I Do
                    </div>
                </div>
            </div>
        </div>
    </XenBaseLayout>
</template>
