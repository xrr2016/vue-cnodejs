<template lang="html">
  <div class="">
    <div class="page-cover" v-if="show && fixHead" @click="showMenus"></div>
    <header :class="{'show':show && fixHead,'fix-header':fixHead,'no-fix':!fixHead}" id="header">
      <div class="nv-toolbar">
        <div class="tollbar-nav" @click="openMenu" v-if="fixHead"></div>
        <span v-text="pageType"></span>
        <i class="num" v-if="messageCount > 0">{{messageCount}}</i>
        <router-link to="/add">
          <i v-if="needAdd" v-show="!messageCount || messageCount <= 0" class="iconfont add-icon">&#xe60f;</i>
        </router-link>
      </div>
    </header>
    <nv-menu :show-menu="show" :page-type="pageType" :nickname="nickname" :profile-url="profileimgurl" v-if="fixHead"></nvmenu>
  </div>
</template>

<script>
import $ from 'webpack-zepto'
import nvMenu from './Nvmenu'
export default {
  replace:true,
  props:{
    pageType:String,
    fixHead:Boolean,
    messageCount:Number,
    needAdd:{
      type:Boolean,
      default:true
    }
  },
  data(){
    return {
      nickname:'',
      profileimgurl:'',
      show:false
    }
  },
  methods:{
    openMenu(){
      $('html,body,#page').addClass('scroll-hide')
      this.show = !this.show
    },
    showMenus(){
      this.show = !this.show
      $('html,body,#page').removeClass('scroll-hide')
    }
  },
  components:{
    nvMenu
  }
}
</script>

<style lang="css">
</style>
