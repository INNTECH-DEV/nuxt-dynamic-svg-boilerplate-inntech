## Render SVGs dynamically in Nuxt 3

## How would we usually do it in Vue?

Our solution to render SVGs dynamically came when we tried to migrate one of our projects from Vue3 to Nuxt3. In Vue3 we had a file_svg.SVG document where we would store all our icons and give each and every single one of them an id. Based on that id we would render the icons using require().

## Why is it not working on Nuxt3?

It's not working because Nuxt3 uses Vite as the default build tool and require() as a feature does not exist.

## Our solution 

We created a new component that stores all the SVGs, each one of them containing a conditional statement to show the SVG only when it matches the id passed through props. There are two ways you can customize its properties, through props or through classes if you are using TailwindCSS as we do.

## The SvgRender.vue component:

```vue
<template>
  <div>
    <svg
      v-if="props.icon == 'check'"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 15.4 11.9"
      fill="currentColor"
      :width="props.width"
      :height="props.height"
    >
      <path
        d="M12.6.1L6 6.8 2.8 3.6c-.2-.2-.4-.2-.6 0L.1 5.7c-.1.1-.1.4 0 .5l5.6 5.6c.2.2.4.2.6 0l9-9c.2-.2.2-.4 0-.6L13.2.1c-.2-.1-.4-.1-.6 0z"
      />
    </svg>
    <svg
      v-if="props.icon == 'briefcase'"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 95.4 96.9"
      fill="currentColor"
      :width="props.width"
      :height="props.height"
    >
      <path
        d="M0 17.9v61.6c0 1.6 1.3 2.9 2.9 2.9H15V15H2.9C1.3 15 0 16.3 0 17.9zM94.2 15h-12v67.4h12.1c1.6 0 2.9-1.3 2.9-2.9V17.9c-.1-1.6-1.4-2.9-3-2.9zM66.3 3.7c0-2.1-1.7-3.7-3.7-3.7H34.5c-2.1 0-3.7 1.7-3.7 3.7V15H19.6v67.4h58V15H66.3V3.7zM38.3 15V7.5h20.6V15H38.3z"
      />
    </svg>
    <svg
      v-if="props.icon == 'star'"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 124.5 118.8"
      fill="currentColor"
      :width="props.width"
      :height="props.height"
    >
      <path
        d="M65.9 2.3L82.8 37l38.2 5.3c3.3.5 4.7 4.6 2.2 6.9L95.4 76l6.8 38c.6 3.3-2.9 5.9-5.9 4.3l-34.1-18.2-34.1 18.2c-3 1.6-6.5-1-5.9-4.3L29 76 1.2 49.2c-2.4-2.3-1.1-6.5 2.2-6.9L41.7 37 58.6 2.3c1.5-3.1 5.8-3.1 7.3 0z"
      />
    </svg>
  </div>
</template>

<script setup>
const props = defineProps({ icon: String, width: Number, height: Number });
</script>
```

## In index.vue:

```vue
<template>
  <div class="w-full p-10">
    <h1 class=" text-4xl text-center pb-10">
      Rendering dynamic svgs in Nuxt 3!
    </h1>

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
  { icon: "check" },
  { icon: "briefcase" },
  { icon: "star" },
];
</script>
```