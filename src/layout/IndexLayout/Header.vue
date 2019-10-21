<template>
  <nav class="navbar">
    <div class="width-limit">
      <a href="/" class="navbar-logo">
        <img src="./imgs/logo_1.png" alt="">
      </a>

      <div class="navbar-right">
        <div class="z-btns">
          <div class="divider"></div>
          <button class="z-btn">登录</button>
          <button class="z-btn">注册</button>
        </div>

        <div class="menu">
          <!--1-->
        </div>
      </div>

      <div class="navbar-container">
        <!--<button class="menu">-->
          <!--<span class="menu-bar"></span>-->
          <!--<span class="menu-bar"></span>-->
          <!--<span class="menu-bar"></span>-->
        <!--</button>-->
        <ul class="nav">
          <li class="nav-tab" v-for="tab in tabs" :key="tab.id" :class="{active: tab.id === activeTab}">
            <router-link to="/about">{{ tab.name }}</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      activeTab: 1,
      tabs: [
        {
          id: 1,
          name: '首页'
        },
        {
          id: 2,
          name: '产品'
        },
        {
          id: 3,
          name: '客户案例'
        },
        {
          id: 4,
          name: '价格'
        },
        {
          id: 5,
          name: '常见问题'
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
  .navbar {
    height: 55px;
    background-color: #324276;
    border-bottom: 1px solid #72789E;
    color: #FFF;
    /* logo */
    .navbar-logo {
      float: left;
      height: 44px;
      padding-top: 10px;
      img {
        height: 100%;
      }
    }

    /* 按钮 */
    .menu {
      cursor: pointer;
      background: none;
      border: none;
      outline: none;
      display: block;
      .menu-bar {
        display: block;
        width: 22px;
        height: 2px;
        background-color: #888;
        border-radius: 1px;
      }
    }

    .navbar-right {
      float: right;
      height: 100%;
      display: flex;
      align-items: center;
      .divider {
        width: 1px;
        background-color: #5467A4;
        height: 40%;
        margin-right: 5px;
      }
      .z-btn {
        cursor: pointer;
        background: none;
        border: none;
        outline: none;
        color: #FFF;
        padding: 12px 16px;
        &:hover {
          background-color: #2157FE;
          border-radius: 4px;
        }
      }
    }

    /* 中间导航 */
    .navbar-container {
      overflow: hidden;
      .nav {
        overflow: hidden;
        list-style: none;
        margin: 0;
        padding: 0;
        .nav-tab {
          float: left;
          cursor: pointer;
          &:hover:not(.active) {
            background-color: #2157FE;
          }
          &.active {
            a {
              color: rgba(255,255,255,0.8);
            }
          }
          a {
            font-size: 17px;
            color: #ffffff;
            text-decoration: none;
            display: block;
            padding: 19px 19px;
          }
        }
      }
    }
  }

  .width-limit {
    min-width: 768px;
    max-width: 1440px;
    height: 100%;
    margin: 0 auto;
    overflow: hidden;
  }

  /* 动画设计 */
  @keyframes logoAni {
    0% {
      transform: translateX(-100px) rotateY(0);
    }
    100% {
      transform: translateX(0) rotateY(360deg);
    }
  }

  /* 响应式设计 */
  @media screen and (max-width: 768px) {
    .navbar {
      .navbar-logo {
        animation: logoAni .5s ease-out forwards;
        height: 25px;
        padding-top: 17px;
      }

      .navbar-right {
        /*float: none;*/
      }

      .nav {
        .nav-tab {
          /*float: none;*/
        }
      }
    }

    .width-limit {
      max-width: inherit;
      min-width: inherit;
    }
  }
</style>
