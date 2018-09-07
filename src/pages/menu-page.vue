<template>
  <div class="menu-page">
    <div class="container">
      <div class="left">
        <div>
          <div class="user-message">
            <div>
              <div class="user-icon">
                <img :src="this.outData.user.user_icon" alt="user's icon">
              </div>
              <div class="user-name">{{ this.outData.user.user_name }}</div>
            </div>
          </div>
          <div class="menu-list">
            <nav-menu :data="this.menu"></nav-menu>
          </div>
        </div>
      </div>
      <div class="right">
        <div>
          <div class="right-top"></div>
          <div class="right-main"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import store from '../vuex/store.js'
export default {
  name: 'Menu',
  store,
  data () {
    return {
      outData: {
        user: {
          user_name: 'Dk',
          user_icon:
            'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1534758602257&di=a93ab2770fba62353de302b8f7b78b95&imgtype=0&src=http%3A%2F%2Fh.hiphotos.baidu.com%2Fzhidao%2Fwh%253D450%252C600%2Fsign%3De68d1890662762d0806bacbb95dc24cc%2Fe7cd7b899e510fb34045d024dc33c895d1430c20.jpg'
        }
      },
      menu: [
        {
          name: '用户中心',
          tree: [
            {
              name: '用户信息',
              id: '2351',
              parent_id: '1233'
            },
            {
              name: '修改密码',
              id: '3435',
              parent_id: '1233'
            }
          ],
          id: '1233'
        },
        {
          name: '应用中心',
          tree: [
            {
              name: '已购应用',
              id: '2345',
              parent_id: '2134'
            },
            {
              name: '全部应用',
              id: '3345',
              parent_id: '2134'
            }
          ],
          id: '2134'
        }
      ]
    }
  }
}
</script>

<style scoped>
.container {
  height: 100%;
  width: 100%;
  position: relative;
  color: #a9b8c2;
  font-size: 18px;
}
.container > div {
  height: 100%;
  transition: all 0.3s ease;
}
.user-message > div,
.container > .right > div {
  width: 100%;
  height: 100%;
  position: relative;
}
/* left */
.container > .left {
  position: absolute;
  width: 300px;
  background-color: #1c2c37;
}
.container > .left > div {
  width: 100%;
  height: 100%;
  position: relative;
  padding-top: 80px;
}
.user-message {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 80px;
  line-height: 80px;
}
.user-message > div {
  padding-left: 80px;
}
.user-icon {
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  width: 80px;
}
.user-icon > img {
  height: 48px;
  width: 48px;
  border-radius: 50%;
  overflow: hidden;
  position: absolute;
  top: 0;
  bottom: 0;
  right: 10px;
  margin: auto;
}
.menu-list {
  width: 100%;
  height: 100%;
  position: relative;
  border-top: 1px solid #efefef;
}
/* right */
.container > .right {
  padding-left: 300px;
}
.container > .right > div > .right-top {
  height: 50px;
  line-height: 50px;
  position: relative;
  z-index: 2;
}
.container > .right > div > .right-main {
  position: absolute;
  height: 100%;
  width: 100%;
  padding-top: 50px;
  top: 0;
  right: 0;
}
</style>
