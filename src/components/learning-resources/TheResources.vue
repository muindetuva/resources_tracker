<template>
  <base-card>
    <BaseButton @click="setSelectedTab('stored-resources')"
      >Stored Resources</BaseButton
    >
    <BaseButton @click="setSelectedTab('add-resources')"
      >Add Resources</BaseButton
    >
  </base-card>

  <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
  components: {
    StoredResources,

    AddResource,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>
