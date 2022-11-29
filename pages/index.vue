<template>
    <div class="w-full p-10">
        <!-- Use the SvgRenderer component and pass the icon prop -->
        <div class="flex gap-10 justify-center text-red-400  ">
            <!-- If you are using TailwindCSS you can set the properties of the svg in class -->
            <!-- You can use it like this : <SvgRender class="w-5 sm:w-10 h-5 sm:h-10" :icon="item.icon" /> -->
            <!-- Or like this : -->
            <div v-for="(item, index) in arrayOfIcons" v-bind:key="index">
                <SvgRender :width="20" :height="20" :icon="item.icon" />
            </div>
        </div>
    </div>
</template>

<script setup>
const arrayOfIcons = [
    { icon: 'check' },
    { icon: 'briefcase' },
    { icon: 'star' },
]
</script>