<template>
    <div>
        <div class="buttons">
            <button @click="itemCount > 0 ? itemCount -= 1 : 0; getClassList()">Remove Item</button>
            <button @click="itemCount += 1; getClassList()">Add Item</button>
            <button @click="padding > 0 ? padding -= 1 : 0;">Decrease Padding</button>
            <button @click="padding += 1;">Increase Padding</button>
        </div>
    <div
        class="container"
    >
      <h1>Flexified Demo</h1>
      <div
          class="flexified-wrapper"
          :class="classList"
          :style="'--flexified-padding:' + padding + 'px'"
      >
          <FlexItem v-for="n in itemCount" :key="n" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import FlexItem from '@/components/FlexItem.vue';
import Flexified from 'flexified';
import 'flexified/src/styles.scss';

export default Vue.extend({
  name: 'Flexbox',
  components: {
      FlexItem
  },
  data: function () {
    return {
      mobileWidthThreshold: 768,
      itemCount: 8,
      padding: 14,
      classList: ['']
    }
  },
  methods: {
    getClassList (): void {
      this.classList = Flexified.getClassNames({
        itemCount: this.itemCount,
        mobileWidthThreshold: this.mobileWidthThreshold
      })
    },
    onResize(event: any) {
      this.getClassList()
    }
  },
  mounted() {
    this.getClassList()
    window.addEventListener('resize', this.onResize)
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 10px;
  box-sizing: border-box;

  &.mobile{
      max-width: 375px;
  }
}

.buttons{
    padding: 20px 0;
    margin-bottom: 20px;
    position: sticky;
    top: 0;
    background-color: #fff;

    button{
      width: 175px;
      height: 40px;
      font-size: 16px;
      margin: 2px;
      background-color: #1576ec;
      color: #fff;
      border-radius: 4px;
      font-family: 'Open Sans';
      font-weight: 600;
      border: 0;
      cursor: pointer;
      transition: background-color .2s ease-in-out;

      &:hover{
        background-color: #1770dc;
      }
    }
}
</style>
