<template>
  <div>
    <div
      class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700"
    >
      <NuxtLink @click="changeItemState(item)" :to="`/item/${title}`">
        <img
          class="rounded-t-lg"
          :src="`${imageSiteUrl}${poster_path}`"
          alt="Series image"
        />
      </NuxtLink>
      <div class="p-5">
        <span href="#">
          <h5
            class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
          >
            {{ title }}
          </h5>
        </span>
        <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
          Release Date: {{ release_date }}
        </p>
        <p
          v-if="overview"
          href="#"
          class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        ></p>
        <p
          v-else
          href="#"
          class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        ></p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps([
  "title",
  "id",
  "overview",
  "release",
  "popularity",
  "poster_path",
  "item",
]);
const imageSiteUrl = "https://image.tmdb.org/t/p/w500/";
const itemState = useState("chosenItem", () => {});
const changeItemState = (item) => {
  itemState.value = item;
};
</script>

<style lang="scss" scoped></style>
