<template>
	<the-header title="Remember Me"></the-header>
	<stored-resources
		:resources="storedResources">
	</stored-resources>
</template>

<script>
import StoredResources from './components/learning-resource/StoredResources.vue';
import TheHeader from './components/layout/TheHeader.vue'
export default {
  components: {
    StoredResources,
		TheHeader
  },
  data() {
    return {
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
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>