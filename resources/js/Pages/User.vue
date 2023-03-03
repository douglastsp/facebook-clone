<script setup>
import { Head, Link } from '@inertiajs/vue3';
import MainNavLayout from '@/Layouts/MainNavLayout.vue';
import CreatePostBox from '@/Components/CreatePostBox.vue';
import Post from '@/Components/Post.vue';

/**
 * Import Icons
 */
import Camera from 'vue-material-design-icons/Camera.vue';
import Pen from 'vue-material-design-icons/TelevisionPlay.vue';

/**
 * Store
 */
import { useGeneralStore } from '@/stores/general';
import { storeToRefs } from 'pinia';
const useGeneral = useGeneralStore();
const { isCropperModal, isImageDisplay } = storeToRefs('useGeneral');

/**
 * Define Props
 */
// const props = defineProps({
//     user: Object,
//     post: Object,
// });

// const { post, user } = toRefs(props);

</script>

<template>
    <Head title="User" />

    <MainNavLayout>
        <div class="w-full min-h-[100vh] pb-20 bg-[#F1F2F5]">
            <div class="w-full bg-white">
                <div class="max-w-[1100px] pt-[56px] mx-auto pb-1">
                    <!-- Cover -->
                    <img src="https://picsum.photos/id/45/2000/320" alt="" class="rounded-b-xl">
                    <!-- /Cover -->

                    <!-- Profile info -->
                    <div id="ProfileInfo" class="flex md:flex-row flex-col items-center justify-between px-4">
                        <div class="flex md:flex-row flex-col gap-4 md:-mt-6 -mt-16 items-center">
                            <div class="relative">
                                <img src="https://picsum.photos/id/200/500/500" alt="profile-photo" 
                                    class="rounded-full w-[165px] h-[165px] border-white border-4">
                                    <button
                                        @click="isCropperModal = true" 
                                        class="absolute right-0 top-[100px] bg-gray-200 hover:bg-gray-300 p-1.5
                                    rounded-full cursor-pointer">
                                        <Camera :size="25" />
                                    </button>
                            </div>
                            <div class="md:mt-4 text-center md:text-left -mt-3">
                                <div class="text-[28px] font-extrabold pt-1">
                                    Douglas Teixeira
                                </div>
                                <div class="text-[17px] font-bold text-gray-600 mb-1.5 text-center md:text-left">
                                    234 Friends
                                </div>
                                <div class="flex md:justify-start justify-center md:-ml-1">
                                    <img src="https://picsum.photos/id/141/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-1 z-[10] w-[40px] h-[40px] border-white border-2">
                                    <img src="https://picsum.photos/id/146/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-3 z-[9] w-[40px] h-[40px] border-white border-2">
                                    <img src="https://picsum.photos/id/142/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-3 z-[8] w-[40px] h-[40px] border-white border-2">
                                    <img src="https://picsum.photos/id/143/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-3 z-[7] w-[40px] h-[40px] border-white border-2">
                                    <img src="https://picsum.photos/id/144/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-3 z-[6] w-[40px] h-[40px] border-white border-2">
                                    <img src="https://picsum.photos/id/145/300/300" alt="profile-photo" 
                                        class="rounded-full -ml-3 z-[5] w-[40px] h-[40px] border-white border-2">
                                </div>
                            </div>
                        </div>

                        <Link 
                            href="/"
                            class="
                                flex
                                justify-center
                                w-7/12
                                md:w-[160px]
                                items-baseline
                                md:my-0
                                my-4
                                bg-gray-200
                                hover:bg-gray-300
                                rounded-lg
                                cursor-pointer
                            "
                        >
                            <button class="flex items-center px-5 py-2 font-bold">
                                <Pen class="-ml-2 mr-1" :size="22" /> Edit profile
                            </button>
                        </Link>
                    </div>
                    <!-- /Profile info -->

                    <!-- Menus -->
                    <div class="flex  border-t h-[50px] py-[4px]">
                        <button class="w-[85px]">
                            <div
                                class="
                                    flex
                                    items-center
                                    text-[15px]
                                    justify-center
                                    h-[45px]
                                    text-blue-500
                                    hover:bg-[#F2F2F2]
                                    w-full
                                    font-bold
                                    rounded-lg
                                    cursor-pointer
                                "
                            >
                                Posts
                            </div>
                            <div class="border-b-4 border-b-blue-400 rounded-md"></div>
                        </button>
                        <button 
                            class="flex items-center text-[15px] justify-center h-[48px] p-1 hover:bg-[#F2F2F2] 
                            w-[85px] font-bold rounded-lg mx-1 cursor-pointer"
                        >
                            About
                        </button>
                        <button 
                            class="flex items-center text-[15px] justify-center h-[48px] p-1 hover:bg-[#F2F2F2] 
                            w-[85px] font-bold rounded-lg mx-1 cursor-pointer"
                        >
                            Friends
                        </button>
                        <button 
                            class="flex items-center text-[15px] justify-center h-[48px] p-1 hover:bg-[#F2F2F2] 
                            w-[85px] font-bold rounded-lg mx-1 cursor-pointer"
                        >
                            Videos
                        </button>
                        <button 
                            class="flex items-center text-[15px] justify-center h-[48px] p-1 hover:bg-[#F2F2F2] 
                            w-[85px] font-bold rounded-lg mx-1 cursor-pointer"
                        >
                            Photos
                        </button>
                        <button 
                            class="flex items-center text-[15px] justify-center h-[48px] p-1 hover:bg-[#F2F2F2] 
                            w-[85px] font-bold rounded-lg mx-1 cursor-pointer"
                        >
                            Check-ins
                        </button>
                    </div>
                    <!-- /Menus -->
                </div>
            </div>

            <div class="flex-cols md:flex w-full max-w-[1100px] justify-between h-[calc(100%-56px)] md:px-0 px-2 mx-auto gap-x-2">
                <!-- Intro -->
                <div id="LeftSection" class="w-full md:w-5/12 mt-4">
                    <div class="bg-white p-3 rounded-lg shadow-lg">
                        <div class="font-extrabold pb-2 text-xl">
                            Intro
                        </div>
                        <div class="pb-5">
                            <button class="w-full bg-gray-200 hover:bg-gray-300 rounded-lg p-2 font-bold">
                                Add bio
                            </button>
                        </div>
                        <div class="pb-5">
                            <button class="w-full bg-gray-200 hover:bg-gray-300 rounded-lg p-2 font-bold">
                                Edit details
                            </button>
                        </div>
                        <div class="pb-5">
                            <button class="w-full bg-gray-200 hover:bg-gray-300 rounded-lg p-2 font-bold">
                                Add Hobbies
                            </button>
                        </div>
                        <div class="pb-5">
                            <button class="w-full bg-gray-200 hover:bg-gray-300 rounded-lg p-2 font-bold">
                                Add feature
                            </button>
                        </div>
                    </div>

                    <div class="bg-white p-3 mt-4 rounded-lg shadow-lg">
                        <div class="font-extrabold pb-2 text-xl">
                            Photos
                        </div>
                        <div class="flex flex-wrap items-center justify-start w-full">
                            <span class="w-1/3">
                                <img 
                                    src="https://picsum.photos/id/78/300/300"
                                    alt="" 
                                    class="aspect-square object-cover p-1 rounded-lg cursor-pointer"
                                >
                            </span>
                        </div>
                    </div>
                </div>
                <!-- /Intro -->

                <!-- Post Section -->
                <div id="PostSection" class="w-full md:w-7/12 overflow-auto">
                    <div id="PostSection" class="row-span-6 max-w-[600px] lg:mx-0 mx-auto overflow-auto">
                        <CreatePostBox 
                            image="https://picsum.photos/id/140/300/320"
                            placeholder="What's on your mind Douglas Teixeira"
                        />

                        <Post />
                        <Post />
                        <Post />
                        <Post />
                        <Post />
                    </div>
                </div>
                <!-- /Post Section -->
            </div>
        </div>
    </MainNavLayout>
  
</template>