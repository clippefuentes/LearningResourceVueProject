<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButton"
    >
      Stored Resources
    </base-button>
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButton"
    >
      Add Resource
    </base-button>
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
          id: '1',
          title: 'Resource 1',
          description: 'First Resources',
          link: 'https://vuejs.org',
        },
        {
          id: '2',
          title: 'Google',
          description: 'Learn Google',
          link: 'https://google.com',
        },
      ],
    };
  },
  computed: {
    storedResButton() {
      return this.selectedTab === 'stored-resources' ? null : 'flat'
    },
    addResButton() {
      return this.selectedTab === 'add-resource' ? null : 'flat'
    },
  },
  provide() {
    return {
      resources: this.storedResources
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>

<style>
</style>