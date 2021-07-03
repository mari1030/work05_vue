<template>
  <div>
    <div class="form__wrapper">
      <div class="form__header">
        <span>STEP{{ stepNumber }}</span>
        <p>お客様の情報を入力してください</p>
      </div>
      <div class="forem__body">
        <dl>
          <div>
            <dt>-性別-</dt>
            <dd>
              <span>
                <label for="male">男性</label>
                <input type="radio" id="male" name="sex" value="男性" v-model="step1Form.sex">
              </span>
              <span>
                <label for="female">女性</label>
                <input type="radio" id="female" name="sex" value="女性" v-model="step1Form.sex">
              </span>
            </dd>
          </div>
          <div>
            <dt>
              <label for="year">
                -生年月日-
              </label>
            </dt>
            <dd>
              <select name="" id="year" v-model="step1Form.year">
                <option value="1990">1990年（平成2年）</option>
                <option value="1991">1991年（平成3年）</option>
                <option value="1992">1992年（平成4年）</option>
              </select>年
              <select name="" id="month" v-model="step1Form.month">
                <option value="1">１</option>
                <option value="2">２</option>
                <option value="3">３</option>
              </select>月
              <select name="" id="day" v-model="step1Form.day">
                <option value="1">１</option>
                <option value="2">２</option>
                <option value="3">３</option>
              </select>日
            </dd>
          </div>
        </dl>

      </div>
      <button @click="onClickButton()" v-if="stepNumber !== 4">
        次へ進む
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      step1Form: {
        sex: '男性',
        year: null,
        day: null,
        month: null,
      },
    }
  },
  props: {
    stepNumber: Number
  },
  methods: {  
  // eslint-disable-next-line no-unused-vars
    onClickButton() {
      this.$emit('parentFunc', this.step1Form);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
