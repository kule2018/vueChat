<template>
  <!--  主页面底部 -->
  <div class="footer">
    <router-link
      class="item"
      to="message"
    >
      <svg
        class="icon"
        aria-hidden="true"
      >
        <use
          v-show="currentTab === 1"
          xlink:href="#icon-message-fill"
        ></use>
        <use
          v-show="currentTab !== 1"
          xlink:href="#icon-messages"
        ></use>
      </svg>
    </router-link>

    <router-link
      class="item"
      :class="this.tabTipsGetter.addFriendReq"
      to="contact_list"
    >
      <svg
        class="icon"
        aria-hidden="true"
      >
        <use
          v-show="currentTab === 3"
          xlink:href="#icon-users-fill"
        ></use>
        <use
          v-show="currentTab !== 3"
          xlink:href="#icon-users"
        ></use>
      </svg>
    </router-link>

    <router-link
      class="item"
      to="robot"
    >
      <svg
        class="icon"
        aria-hidden="true"
      >
        <use
          v-show="currentTab === 2"
          xlink:href="#icon-fire1"
        ></use>
        <use
          v-show="currentTab !== 2"
          xlink:href="#icon-fire"
        ></use>
      </svg>
    </router-link>

    <router-link
      class="item"
      to="me"
    >
      <svg
        class="icon"
        aria-hidden="true"
      >
        <use
          v-show="currentTab === 4"
          xlink:href="#icon-user1"
        ></use>
        <use
          v-show="currentTab !== 4"
          xlink:href="#icon-user2"
        ></use>
      </svg>
    </router-link>
  </div>
</template>

<script>
import axios from "axios"
import {
  mapGetters
} from 'vuex'
export default {
  name: 'Footer',
  props: ['currentTab'],
  data () {
    return {
    }
  },
  computed: {
    ...mapGetters([
      'tabTipsGetter'
    ])
  }
}
</script>

<style lang="scss" scoped>
svg {
  color: #fb7299;
}
.footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  z-index: 99;
  font-size: 0.36rem;
  display: flex;
  justify-content: space-between;
  background: white;
  border-top: 0.01rem solid #eee;
  padding-top: 0.1rem;
  padding-bottom: 0.1rem;
  .item {
    margin: 0 auto;
  }
  .tips::after {
    content: "";
    width: 0.18rem;
    height: 0.18rem;
    display: inline-block;
    position: relative;
    border-radius: 50%;
    background-color: red;
    position: absolute;
  }
}
</style>
