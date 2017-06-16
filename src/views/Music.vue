<template>
  <div class="wrapper">
    <mu-row class='paper-row'>
      <mu-col class='paper-el' width='33' tablet='25' desktop='20' v-for='item in items' :key='item.id'>
        <router-link :to='{name: 'musicItem'}, params: {id: item.id}'>
          <mu-paper>
            <div class='paper-border'>
              <div class='paper-img' :style="'background-image: url(' +item.images.large+ ')'">
              </div>
            </div>
            <div class='paper-text'>
              <p> {{item.title}}</p>
              <p class='star-box'>
                <span class='paper-star' v-if='item.rating.average > 0'>
                </span>
              </p>
            </div>
          </mu-paper>
        </router-link>
      </mu-col>
    </mu-row>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="" scoped>
  
</style>