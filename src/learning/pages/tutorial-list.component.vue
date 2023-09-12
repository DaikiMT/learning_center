<template>

</template>

<script>
import {TutorialsApiServices} from "../services/tutorials-api.services.js";

export default {
  name: "tutorial-list",
  title: "Tutorials",
  data() {
    return {
      tutorial: [],
      tutorialDialog: false,
      deleteTutorialDialog: false,
      deleteTutorialsDialog: false,
      tutorials: {},
      selectedTutorial: {},
      filters: {},
      submitted: false,
      statuses: [
        { label: "Published", value: "published" },
        { label: "Unpublished", value: "unpublished" },
        ],
        tutorialService: null,
    }
  },
    created() {
      this.tutorialService = new TutorialsApiServices();
      this.tutorialService.getAll()
          .then(response => {
            this.tutorials = response.data;
            console.log(response.data);
          })
    }
}
</script>

<style scoped>

</style>