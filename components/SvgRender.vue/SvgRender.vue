<template>
    <!-- List your svgs that you need to render dynamically here. -->
    <!-- Make sure to pass props. -->
    <div>
        <svg v-if="props.icon == 'check'" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 15.4 11.9" fill="currentColor"
            :width="props.width" :height="props.height">
            <path
                d="M12.6.1L6 6.8 2.8 3.6c-.2-.2-.4-.2-.6 0L.1 5.7c-.1.1-.1.4 0 .5l5.6 5.6c.2.2.4.2.6 0l9-9c.2-.2.2-.4 0-.6L13.2.1c-.2-.1-.4-.1-.6 0z" />
        </svg>
        <svg v-if="props.icon == 'briefcase'" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 95.4 96.9"
            fill="currentColor" :width="props.width" :height="props.height">
            <path
                d="M0 17.9v61.6c0 1.6 1.3 2.9 2.9 2.9H15V15H2.9C1.3 15 0 16.3 0 17.9zM94.2 15h-12v67.4h12.1c1.6 0 2.9-1.3 2.9-2.9V17.9c-.1-1.6-1.4-2.9-3-2.9zM66.3 3.7c0-2.1-1.7-3.7-3.7-3.7H34.5c-2.1 0-3.7 1.7-3.7 3.7V15H19.6v67.4h58V15H66.3V3.7zM38.3 15V7.5h20.6V15H38.3z" />
        </svg>
        <svg v-if="props.icon == 'star'" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 124.5 118.8"
            fill="currentColor" :width="props.width" :height="props.height">
            <path
                d="M65.9 2.3L82.8 37l38.2 5.3c3.3.5 4.7 4.6 2.2 6.9L95.4 76l6.8 38c.6 3.3-2.9 5.9-5.9 4.3l-34.1-18.2-34.1 18.2c-3 1.6-6.5-1-5.9-4.3L29 76 1.2 49.2c-2.4-2.3-1.1-6.5 2.2-6.9L41.7 37 58.6 2.3c1.5-3.1 5.8-3.1 7.3 0z" />
        </svg>
        <svg v-if="props.icon == 'ro'" width="20" height="17" fill="currentColor" viewBox="0 0 3 2">
            <rect width="3" height="2" x="0" y="0" fill="#002B7F"></rect>
            <rect width="2" height="2" x="1" y="0" fill="#FCD116"></rect>
            <rect width="1" height="2" x="2" y="0" fill="#CE1126"></rect>
        </svg>
        <svg v-if="props.icon == 'en'" width="20" height="20" fill="currentColor" viewBox="0 0 60 30">
            <clipPath id="s">
                <path d="M0,0 v30 h60 v-30 z"></path>
            </clipPath>
            <clipPath id="t">
                <path d="M30,15 h30 v15 z v15 h-30 z h-30 v-15 z v-15 h30 z"></path>
            </clipPath>
            <g clip-path="url(#s)">
                <path d="M0,0 v30 h60 v-30 z" fill="#012169"></path>
                <path d="M0,0 L60,30 M60,0 L0,30" stroke="#fff" stroke-width="6"></path>
                <path d="M0,0 L60,30 M60,0 L0,30" clip-path="url(#t)" stroke="#C8102E" stroke-width="4"></path>
                <path d="M30,0 v30 M0,15 h60" stroke="#fff" stroke-width="10"></path>
                <path d="M30,0 v30 M0,15 h60" stroke="#C8102E" stroke-width="6"></path>
            </g>
        </svg>
    </div>
</template>

<script setup>
const props = defineProps({ icon: String, width: Number, height: Number });
</script>