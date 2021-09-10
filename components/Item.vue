
<template>
  <div class="item-width px-3 py-6">
    <div class="w-full bg-gray-100 item">
      <nuxt-link :to="'/category/' + work.fields.category.sys.id">
        <div
          class="absolute bg-gray-300 py-1  px-3 rounded shadow mt-1 ml-1 text-sm"
        >
          {{ work.fields.category.fields.name }}
        </div>
      </nuxt-link>
      <nuxt-link :to="'/work/' + work.fields.slug">
      <div class="img-wrap">
      <div
        class="mb-3 w-full h-48 sm:h-48 md:h-48 lg:h-64 bg-center bg-cover hover-scale"
        :style="
          'background-image: url(' + work.fields.image.fields.file.url + ')'
        "
      ></div>
      </div>
       </nuxt-link>
      <nuxt-link :to="'/work/' + work.fields.slug">
        <h3 class="ml-3 font-bold text-lg h-12">{{ work.fields.title }}</h3>
      </nuxt-link>
      <h4 class="ml-3 text-xs h-10">{{ work.fields.subtitle }}</h4>
      <div class="flex ml-2">
        <li
          v-for="tag in work.fields.tag"
          :key="tag.sys.id"
          class="list-none text-xs m-1 bg-gray-300 p-1 rounded cursor-pointer"
          @click="$router.push('/tag/' + tag.sys.id)"
        >
          {{ tag.fields.name }}
        </li>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["work"],
};
</script>

<style>
.item-width {
  width: 33%;
}

@media screen and (min-width: 768px) and (max-width: 1100px) {
  .item-width {
    width: 50%;
  }
}

@media screen and (max-width:480px) { 
  .item-width {
    width: 100%;
  }
}

.item {
  color: #000;
}

.img-wrap {
  overflow: hidden;
  transition:1s all;
}

.hover-scale {
  transition: all .3s ease;
}

.hover-scale:hover {
  transform:scale(1.1,1.1);
  transition: all .5s ease;
}
</style>
