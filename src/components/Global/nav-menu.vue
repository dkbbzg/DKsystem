<template>
  <div class="nav-menu">
    <div class="list parent" v-for="(parent, index) in this.data" :key="parent.id">
      <div class="row-name" @click="listChange(index)">
        <span>{{ parent.name }}</span>
        <i class="el-icon-arrow-down"></i>
      </div>
      <div class="child" :class="active == child.id ? 'active' : ''" v-for="child in parent.tree" :key="child.id" @click="active = child.id">
        <div class="row-name">
          <span>{{ child.name }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import store from '../../vuex/store.js'
import $ from 'jquery'

export default {
  name: 'NavMenu',
  store,
  props: ['data'],
  data () {
    return {
      active: ''
    }
  },
  methods: {
    listChange (index) {
      $('.list').eq(index).toggleClass('open')
    }
  }
}
</script>

<style scoped>
.nav-menu {
  width: 100%;
  height: 100%;
  overflow-y: scroll;
  font-size: 16px;
}
.row-name {
  height: 60px;
  line-height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
}
.row-name:hover {
  background-color: #777;
  color: #222;
}
.parent>.row-name {
  padding: 0 20px;
}
.child>.row-name {
  padding: 0 40px;
}
.list>.child {
  height: 0;
  overflow: hidden;
  transition: all .3s ease;
}
.list.open>.child {
  height: 60px;
}
.list>.row-name>i {
  transition: all .3s ease;
}
.list.open>.row-name>i {
  transform: rotate(-180deg);
}
.child.active {
  color: #f9b060;
}
</style>
