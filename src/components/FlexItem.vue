<template>
  <div class="flexified-child">
    <div class="flex-item-content">
      <div class="icon">
        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="59" height="58" viewBox="0 0 59 58">
          <defs>
              <path id="a" d="M0 0h50.081v51.523H0z"/>
          </defs>
          <g fill="none" fill-rule="evenodd" transform="translate(4.538 3)">
              <mask id="b" fill="#fff">
                  <use xlink:href="#a"/>
              </mask>
              <path fill="#768CDC" d="M13.941 15.805c0-6.204 5.047-11.251 11.251-11.251s11.251 5.047 11.251 11.25c0 6.066-4.825 11.025-10.838 11.243a28.165 28.165 0 0 0-.564-.006c-.11 0-.219.003-.328.004-5.982-.252-10.772-5.197-10.772-11.24m28.696 17.637c-2.398-2.1-5.193-3.717-8.233-4.802 3.99-2.872 6.593-7.555 6.593-12.835C40.997 7.09 33.907 0 25.192 0S9.387 7.09 9.387 15.805c0 5.236 2.56 9.885 6.495 12.763-3.12 1.084-5.986 2.728-8.438 4.874C2.644 37.644 0 43.257 0 49.246a2.277 2.277 0 0 0 4.554 0c0-9.622 8.982-17.469 20.102-17.646a16.09 16.09 0 0 0 .976.003c11.024.271 19.895 8.08 19.895 17.643a2.277 2.277 0 0 0 4.554 0c0-5.989-2.644-11.602-7.444-15.804" mask="url(#b)"/>
          </g>
        </svg>
      </div>
      <div class="primary">30 points</div>
      <div class="secondary">Create an account</div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import 'flexified/src/styles.scss';

export default Vue.extend({
  name: 'FlexItem'
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.flexified-child {
  outline: solid 1px #848ca3;
  background-color: #f9faff;
  font-family: "Montserrat";

  .flex-item-content {
    display: flex;
    flex-flow: column;
    justify-content: center;
    height: 100%;
  }
}

.icon{
  margin: 0 auto;
  width: 59px;
  height: 59px;

  svg{
    width: 100%;
  }
}

.primary{
  font-weight: bold;
  font-size: 27px;
  color: #011247;
  padding-top: 15px;
}

.secondary{
  font-size: 16px;
  color: #4e5772;
  padding-top: 2px;
}

.flexified-mobile{
  @media all and (max-width: 500px){
    .icon{
      width: 38px;
      height: 38px;
    }
    .primary{
      font-size: 16px;
      padding-top: 11px;
    }
    .secondary{
      font-size: 12px;
    }
  }
}
</style>
