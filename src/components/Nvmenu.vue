<template lang="html">
  <section id="sideBar" class="nav-list" :class="{'show':showMenu}">
    <user-info></user-info>
    <section class="list-ul">
      <router-link class="iconfont item icon-all"
      :to="{'name':list,query:{tab:'all'}}">全部</router-link>
      <router-link class="iconfont item icon-good"
      :to="{'name':list,query:{tab:'good'}}">精华</router-link>
      <router-link class="iconfont item icon-share"
      :to="{'name':list,query:{tab:'share'}}">分享</router-link>
      <router-link class="iconfont item icon-ask"
      :to="{'name':list,query:{tab:'ask'}}">问答</router-link>
      <router-link class="iconfont item icon-job"
      :to="{'name':list,query:{tab:'job'}}">招聘</router-link>
      <router-link class="iconfont item icon-msg line"
      :to="{'name':'message'}">消息</router-link>
      <router-link class="iconfont item icon-about"
      :to="{'name':'about'}">关于</router-link>
    </section>
  </section>
</template>

<script>
import userInfo from './Userinfo'
export default {
  replace:true,
  props:['showMenu','pageType','nickName','profileUrl'],
  components:{
    userInfo
  }
}
</script>

<style lang="scss">
.nav-list{
  position: fixed;
  top: 0;
  bottom: 0;
  -left: -200px;
  width: 200px;
  background-color: #fff;
  color: #313131;
  transition: all .3s ease;
  z-index: 10;
  &.show{
    transform: translateX(200px);
  }
}
.list-ul{
  margin: 0 24px;
  border-top: 1px solid #d4d4d4;
  overflow: hidden;
  padding-top: 9%;
  .item{
    display: block;
    font-size: 14px;
    font-weight: 700;
    padding: 9% 0;
    text-align: left;
    text-indent: 1px;
    line-height: 1px;
    color: #313131;
    &:last-child{
      margin-bottom: 50px;
    }
    &:before{
      color: #2c3e50;
    }
  }
  .line{
    border-top: 1px solid #d4d4d4;
  }
}
</style>
