<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">音乐专辑管理</router-link> |
      <router-link to="/crawler">爬虫代码</router-link> |
      <router-link to="/save">存储代码</router-link> |
      <router-link to="/test">测试代码</router-link> |
      <router-link to="/rest">rest测试</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
