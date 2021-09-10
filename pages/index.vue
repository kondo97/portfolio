<template>
  <div class="flex flex-wrap">
    <Item 
      v-for="work in works" 
      :key="work.sys.id"
      :work="work" 
    />
  </div>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'
const client = createClient()
export default { 
  asyncData() {
    return Promise.all([
      client.getEntries({
        'content_type': 'work',
         order: '-fields.date',
      })
    ]).then(([works]) => {
      return {
        works: works.items
      }
    }).catch(console.error)
  }
}
</script>

<style>

</style>

