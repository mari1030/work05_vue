<template>
  <div>
    <div class="form__wrapper">
      <div class="form__header">
        <span>STEP{{ stepNumber }}</span>
        <p>ご相談内容をご記入ください</p>
      </div>
      <div class="forem__body">
        <dl>
          <div>
            <dt>-ご相談内容-</dt>
            <dd>
              <textarea id="" cols="30" rows="10"  v-model="step2Form.step3"></textarea>
            </dd>
          </div>
        </dl>
      </div>
    </div>
    <button @click="backStep()" v-if="stepNumber !== 1">
      前へ戻る
    </button>
    <button @click="onClickButton()" v-if="stepNumber !== 4">
      次へ進む
    </button>
  </div>
</template>

<script>

export default {
  data() {
    return {
      step2Form: {
        step3: '',
      }
    }
  },
  props: {
    stepNumber: Number
  },
  methods: {  
  // eslint-disable-next-line no-unused-vars
    onClickButton() {
      this.$emit('parentFunc', this.step2Form);
    },
    backStep() {
      this.$emit('backFunc', this.stepNumber);
    }
  }
}
</script>
