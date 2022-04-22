<template>
  <ul>
    <ResourceItem
      v-for="res in resources"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    />
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem.vue';

export default {
  props: ['resources'],
  components: { ResourceItem },
};
</script>
