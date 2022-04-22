<template>
  <base-card>
    <BaseButton
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButton"
    >
      Stored Resources
    </BaseButton>
    <BaseButton @click="setSelectedTab('AddResource')" :mode="addResButton"
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
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official vue docs',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to googles',
          link: 'https://google.com',
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
  computed: {
    storedResButton() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    addResButton() {
      return this.selectedTab === 'AddResource' ? null : 'flat';
    },
  },
};
</script>
