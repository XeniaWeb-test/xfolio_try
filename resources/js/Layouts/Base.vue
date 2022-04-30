<script setup>
import { ref } from 'vue';
import AppLogoXeniaWeb from '@/Components/AppLogoXeniaWeb.vue';
import BreezeDropdown from '@/Components/Dropdown.vue';
import BreezeDropdownLink from '@/Components/DropdownLink.vue';
import BreezeNavLink from '@/Components/NavLink.vue';
import BreezeResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';
import { Link } from '@inertiajs/inertia-vue3';

const showingNavigationDropdown = ref(false);
</script>

<template>
    <div>
        <div v-if="$slots.page_background">
            <slot name="page_background"/>
        </div>

        <div class="min-h-screen styleee"  >
            <nav class="bg-white/80 backdrop-blur-sm border-b border-gray-100">
                <!-- Primary Navigation Menu -->
                <div class=" max-w-7xl mx-auto px-4 sm:px-6 lg:px-12">
                    <div class="flex justify-between h-16">
                        <div class="flex w-full">
                            <!-- Logo -->
                            <div class="shrink-0 flex items-center">
                                <Link :href="route('works.index')">
                                    <AppLogoXeniaWeb class="w-25 h-10 fill-current text-gray-500" />
                                </Link>
                            </div>

                            <!-- Navigation Links -->
                            <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex">
                                <BreezeNavLink :href="route('page.about')" :active="route().current('page.about')">
                                    About me
                                </BreezeNavLink>
                                <BreezeNavLink :href="route('page.contacts')" :active="route().current('page.contacts')">
                                    Contacts
                                </BreezeNavLink>
                                <a href="https://blog.xeniaweb.ru" target="_blank" class="flex items-center px-1 pt-1 border-b-4 border-transparent text-sm font-medium leading-5 text-gray-500 hover:text-gray-700 hover:border-gray-300 focus:outline-none focus:text-gray-700 focus:border-gray-300 transition duration-150 ease-in-out">
                                    Blog (Ru)
                                </a>
                            </div>
                                <div v-if="$slots.link_portfolio"  class="mr-2 sm:-my-px flex ml-auto hover:bg-gray-100 sm:hover:bg-transparent">
                                    <BreezeNavLink :href="route('works.index') + '#worksList'">
                                        <slot name="link_portfolio" />
                                    </BreezeNavLink>
                                </div>
                        </div>
                        <!-- Hamburger -->
                        <div class="-mr-2 flex items-center sm:hidden">
                            <button @click="showingNavigationDropdown = ! showingNavigationDropdown" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
                                <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                                    <path :class="{'hidden': showingNavigationDropdown, 'inline-flex': ! showingNavigationDropdown }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                                    <path :class="{'hidden': ! showingNavigationDropdown, 'inline-flex': showingNavigationDropdown }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                                </svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Responsive Navigation Menu -->
                <div :class="{'block': showingNavigationDropdown, 'hidden': ! showingNavigationDropdown}" class="sm:hidden pl-[60%]">
                    <div class="pt-2 pb-3 space-y-1">
                        <BreezeResponsiveNavLink :href="route('page.about')" :active="route().current('page.about')">
                            About me
                        </BreezeResponsiveNavLink>
                        <BreezeResponsiveNavLink :href="route('page.contacts')" :active="route().current('page.contacts')">
                            Contacts
                        </BreezeResponsiveNavLink>
                        <a href="https://blog.xeniaweb.ru" target="_blank" class="flex pl-3 pr-4 py-2 border-r-4 border-transparent text-base font-medium text-gray-600 hover:text-gray-800 hover:bg-gray-100 hover:border-gray-400 focus:outline-none focus:text-gray-800 focus:bg-gray-100 focus:border-gray-400 transition duration-150 ease-in-out">
                            Blog (Ru)
                        </a>
                    </div>

                    <!-- Responsive Settings Options -->
                    <!-- Временно закрыто-->
                    <div class="hidden">
                        <div class="pt-4 pb-1 border-t border-gray-200 ">
                            <div class="px-4">
                                <div class="font-medium text-base text-gray-800">{{ $page.props.auth.user.name }}</div>
                                <div class="font-medium text-sm text-gray-500">{{ $page.props.auth.user.email }}</div>
                            </div>

                            <div class="mt-3 space-y-1">
                                <BreezeResponsiveNavLink :href="route('logout')" method="post" as="button">
                                    Log Out
                                </BreezeResponsiveNavLink>
                            </div>
                        </div>
                    </div>
                </div>
            </nav>

            <!-- Page Heading -->
            <header class="p-4" v-if="$slots.header">
                <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8 ">
                    <slot name="header" />
                </div>
            </header>

            <!-- Page Content -->
            <main>
                <slot />
            </main>
        </div>
    </div>
</template>
