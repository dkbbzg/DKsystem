<template>
  <div class="nav-menu">
    <div class="list first" v-for="first in this.data" :key="first.name">
      <div class="row-name" :class="first.isRoot ? 'root' : ''">
        <span>{{ first.name }}</span>
        <i class="el-icon-arrow-down" v-if="!first.isRoot"></i>
      </div>
      <div class="list second" v-for="second in first.tree" :key="second.name" v-if="!first.isRoot">
        <div class="row-name" :class="second.isRoot ? 'root' : ''">
          <span>{{ second.name }}</span>
          <i class="el-icon-arrow-down" v-if="!second.isRoot"></i>
        </div>
        <div class="list third" v-for="third in second.tree" :key="third.name" v-if="!second.isRoot">
          <div class="row-name root" :class="third.isRoot ? 'root' : ''">
            <span>{{ third.name }}</span>
            <i class="el-icon-arrow-down" v-if="!third.isRoot"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import store from '../../vuex/store.js'
export default {
  name: 'NavMenu',
  store,
  props: ['data'],
  created () {
    console.log(this.data)
  }
}
</script>

<style scoped>
.nav-menu {
  width: 100%;
  height: 100%;
  overflow-y: scroll;
  padding-right: 8%;
  font-size: 16px;
}
.row-name {
  height: 60px;
  line-height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.list {
  padding-left: 20px;
}
</style>
