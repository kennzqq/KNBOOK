<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import GuestLayout from '@/layouts/GuestLayout.vue';

withDefaults(
    defineProps<{
        canRegister: boolean;
    }>(),   
    {
        canRegister: true,
    },
);
</script>

<template>
    <GuestLayout :can-register="canRegister">
        <Head title="Home" />
        
        <main class="relative overflow-hidden">
            
            <div class="flex relative z-20 items-center justify-center overflow-hidden">
                <div class="container mx-auto px-4 sm:px-6 flex flex-col md:flex-row items-center justify-center relative py-8 md:py-15 gap-6 md:gap-12">
                    
                    <div class="flex flex-col relative z-20 w-full md:max-w-lg text-center md:text-left">
                        <span class="w-16 h-1.5 bg-book-primary mb-4 md:mb-8 mx-auto md:mx-0"></span>
                        
                        <h1 class="font-bebas-neue uppercase text-3xl sm:text-4xl md:text-6xl font-black flex flex-col leading-none text-book-text-primary">
                            Discover
                            <span class="text-2xl sm:text-3xl md:text-5xl">
                                Books
                            </span>
                        </h1>
                        
                        <p class="text-xs sm:text-sm text-book-text-secondary mt-2 md:mt-3">
                            Explore thousands of books from the Google Books library. From bestsellers to hidden gems, find your next great read in our extensive collection.
                        </p>
                        
                        <div class="flex mt-4 md:mt-6 gap-3 justify-center md:justify-start">
                            <Link href="/books"
                                class="uppercase py-1.5 px-3 rounded-lg bg-book-primary border-2 border-transparent text-white text-sm hover:bg-book-secondary transition-colors">
                                Browse Books
                            </Link>

                            <Link href="/about"
                                class="uppercase py-1.5 px-3 rounded-lg bg-transparent border-2 border-book-primary text-book-primary hover:bg-book-primary hover:text-white transition-colors text-sm">
                                Learn More
                            </Link>
                        </div>
                    </div>
                    
                    <div class="relative w-full md:max-w-md h-[280px] sm:h-[320px] md:h-[380px] flex items-center justify-center">
                        <img 
                            src="/images/hero.png" 
                            alt="Books illustration" 
                            class="w-full h-full object-contain"
                        />
                    </div>
                </div>
            </div>

            <div class="container mx-auto px-6 py-8 pb-12">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

                    <div class="text-center p-6 border border-book-primary/30 rounded-xl shadow-lg hover:shadow-2xl hover:-translate-y-2 transition-all duration-300 bg-white/50 backdrop-blur-sm">
                        <div class="flex justify-center mb-4">
                            <svg class="w-12 h-12 text-book-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253">
                                </path>
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-book-text-primary mb-2">Vast Collection</h3>
                        <p class="text-book-text-secondary">Access millions of books from Google Books library</p>
                    </div>

                    <div class="text-center p-6 border border-book-primary/30 rounded-xl shadow-lg hover:shadow-2xl hover:-translate-y-2 transition-all duration-300 bg-white/50 backdrop-blur-sm">
                        <div class="flex justify-center mb-4">
                            <svg class="w-12 h-12 text-book-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-book-text-primary mb-2">Easy Search</h3>
                        <p class="text-book-text-secondary">Find exactly what you're looking for with powerful filters</p>
                    </div>

                    <div class="text-center p-6 border border-book-primary/30 rounded-xl shadow-lg hover:shadow-2xl hover:-translate-y-2 transition-all duration-300 bg-white/50 backdrop-blur-sm">
                        <div class="flex justify-center mb-4">
                            <svg class="w-12 h-12 text-book-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M13 10V3L4 14h7v7l9-11h-7z"></path>
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-book-text-primary mb-2">Instant Access</h3>
                        <p class="text-book-text-secondary">Preview and explore books instantly</p>
                    </div>

                </div>
            </div>
        </main>
    </GuestLayout>
</template>