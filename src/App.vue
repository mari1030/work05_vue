<template>
  <div>
    <component :is="'Step' + stepNumber" :stepNumber="stepNumber" @parentFunc="updateForm" @backFunc="downStep"></component>
  </div>
</template>

<script>
import Step1 from "./components/Step1";
import Step2 from "./components/Step2";
import Step3 from "./components/Step3";

export default {
  name: 'App',
  components: {
    Step1,
    Step2,
    Step3,
  },
  data() {
    return {
      form: [],
      stepNumber: 1
    }
  },
  methods: {
    updateForm: function(e) {
      console.log(e);
      this.form.push(e);
      this.stepNumber++;
    },
    downStep: function(e) {
      this.stepNumber = e - 1
    }
  }
}
</script>