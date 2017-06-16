<template>
  <div class='menu'>
    <mu-drawer class='drawer' :open='open' :docked='docked' @close='toggle()' >
      <div class='drawer-pic' style='background:#474a4f; padding: 70px 0; text-align: center; color: #fff;'>
        <div class='title' style='font-size: 24px;'>music with im</div>
      </div>
      <mu-list value='menu' @itemClick="docked ? '' : toggle()" @change="page">
        <mu-list-item value='mylike' title='我喜欢的'>
          <mu-icon slot='left' value=''/>
        </mu-list-item>
        <mu-list-item value='myfriends' title='我的好友'>
          <mu-icon slot='left' value=""/>
        </mu-list-item>
        <mu-list-item value='about' title='关于'>
          <mu-icon slot='left' value=''/>
        </mu-list-item>
      </mu-list>
    </mu-drawer>
    <mu-paper :zDepth="2">
      <mu-appbar title="haha">
        <mu-icon-button icon="menu" slot="left" @click='toggle(true)' />
        <mu-text-field icon="search" class="appbar-search-field" slot="default" hintText="请输入" />
        <mu-icon-menu icon="more_vert" slot="right">
          <mu-menu-item title="menu1" />
          <mu-menu-item title="menu2" />
        </mu-icon-menu>
      </mu-appbar>
      <mu-tabs :value="activeTab" @change="handleTabChange">
        <mu-tab value="recommend" title="推荐" />
        <mu-tab value="ranklist" title="排行榜" />
        <mu-tab value="mylike" title="我喜欢的" />
      </mu-tabs>
      <div v-if="activeTab === 'recommend'">
        <h2>tab one</h2>
      </div>
      <div v-if="activeTab === 'ranklist'">
        <h2>tab two</h2>
      </div>
      <div v-if="activeTab === 'mylike'">
        <h2>tab three</h2>
      </div>
    </mu-paper>
  </div>
</template>

<script>
export default {
  data () {
    return {
      open: false,
      docked: true,
      activeTab: 'ranklist'
    }
  },
  methods: {
    toggle (flag) {
      this.open = !this.open;
      this.docked = !flag;
    },
    handleTabChange () {
      this.activeTab = ''
    }
  }
}
</script>

<style lang='less' scoped>
.appbar-search-field{
  color: #FFF;
  margin-bottom: 0;
  &.focus-state {
    color: #FFF;
  }
  .mu-text-field-hint {
    color: fade(#FFF, 54%);
  }
  .mu-text-field-input {
    color: #FFF;
  }
  .mu-text-field-focus-line {
    background-color: #FFF;
  }
}
</style>