<template>
    <div class="w-full p-10">
        <div class="flex flex-col  items-center gap-10">
            <!-- Use the SvgRenderer component and pass the icon prop -->
            <div class="flex gap-10 justify-center text-red-400  ">
                <!-- If you are using TailwindCSS you can set the properties of the svg in class -->
                <!-- You can use it like this : <SvgRender class="w-5 sm:w-10 h-5 sm:h-10" :icon="item.icon" /> -->
                <!-- Or like this : -->
                <div v-for="(item, index) in arrayOfIcons" v-bind:key="index">
                    <SvgRender :width="20" :height="20" :icon="item.icon" />
                </div>
            </div>
            <!-- Example of dynamic switching between SVGs -->
            <div class="flex flex-col items-center">
                <p class="pb-2 font-bold">Example of dynamic switching SVGs:</p>
                <div class="relative w-60 cursor-pointer group px-5 border-t-[1px]">

                    <div class="flex p-2 justify-between items-center hover:bg-slate-50 ">
                        <div>
                            <p>Language:</p>
                        </div>
                        <div class="flex gap-1 items-center px-3 ">
                            <div class="flex gap-2 items-center">
                                <p class="text-primary">{{ flags[selectedLanguage].name }}</p>
                                <SvgRender :icon="flags[selectedLanguage].icon" />
                            </div>
                            <div
                                class="group-hover:visible group-hover:opacity-100 duration-500 opacity-0 absolute invisible left-0 p-5 h-max top-10 w-60 shadow-md ">
                                <div v-for="(item, index) in flags" v-bind:key="index">
                                    <div class="flex justify-between w-full py-2 px-2 hover:bg-slate-50 rounded-lg"
                                        @click="selectedLanguage = item.id">
                                        <p>{{ item.name }}</p>
                                        <SvgRender :icon="item.icon" />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const arrayOfIcons = [
    { icon: 'check' },
    { icon: 'briefcase' },
    { icon: 'star' },
];

const flags = [
    { icon: 'en', name: 'English', id: 0 },
    { icon: 'ro', name: 'Romanian', id: 1 },
];

const selectedLanguage = ref(0)
</script>