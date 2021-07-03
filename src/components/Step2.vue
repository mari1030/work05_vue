<template>
  <div>
    <div class="form__wrapper">
      <div class="form__header">
        <span>STEP{{ stepNumber }}</span>
        <p>以下にお答えください</p>
      </div>
      <div class="forem__body">
        <dl>
          <div>
            <dt>現在、生命保険に加入されていますか？</dt>
            <dd>
              <span>
                <label for="yes">
                  はい
                </label>
                <input type="radio" value="y" id="yes" v-model="step2Form.step2Q1">
              </span>
              <span>
                <label for="no">
                  いいえ
                </label>
                <input type="radio" value="n" id="no" v-model="step2Form.step2Q1">
              </span>
            </dd>
          </div>

          <div v-if="step2Form.step2Q1 !== ''">
            <dt>現在入院中ですか。または、最近3か月以内に医師の診察・検査の結果、入院・手術をすすめられたことはありますか？</dt>
            <dd>
              <span>
                <label for="yes">
                  はい
                </label>
                <input type="radio" value="y" id="yes" v-model="step2Form.step2Q2">
              </span>
              <span>
                <label for="no">
                  いいえ
                </label>
                <input type="radio" value="n" id="no" v-model="step2Form.step2Q2">
              </span>
            </dd>
          </div>

          <div v-if="step2Form.step2Q2 !== ''">
            <dt>過去5年以内に、病気やけがで、手術をうけたことまたは継続して7日以内の入院をしたことがありますか？</dt>
            <dd>
              <span>
                <label for="yes">
                  はい
                </label>
                <input type="radio" value="y" id="yes" v-model="step2Form.step2Q3">
              </span>
              <span>
                <label for="no">
                  いいえ
                </label>
                <input type="radio" value="n" id="no" v-model="step2Form.step2Q3">
              </span>
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
        step2Q1: '',
        step2Q2: '',
        step2Q3: '',
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
