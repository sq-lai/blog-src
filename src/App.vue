<template>
  <div id="app">
    <nav class="navbar">
      <div class="nav-content">
        <router-link to="/" class="logo">sq-lai的博客</router-link>
        <div class="nav-links">
          <router-link to="/" class="nav-link">首页</router-link>
          <router-link to="/about" class="nav-link">关于我</router-link>
          <router-link to="/archive" class="nav-link">文章归档</router-link>
          <router-link to="/projects" class="nav-link">项目展示</router-link>
        </div>
      </div>
    </nav>

    <router-view/>

    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2025 早上爬不起的博客 | 做有趣的人，干有趣的事</p>
      </div>
    </footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
    Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  background-color: #f8f9fa;
  color: #2c3e50;
  line-height: 1.6;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.navbar {
  background-color: white;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.nav-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  color: #1e88e5;
  font-size: 20px;
  font-weight: bold;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 30px;
}

.nav-link {
  color: #2c3e50;
  text-decoration: none;
  font-size: 16px;
  transition: color 0.3s;
}

.nav-link:hover,
.nav-link.router-link-active {
  color: #1e88e5;
}

.footer {
  margin-top: auto;
  background-color: white;
  padding: 20px 0;
  box-shadow: 0 -2px 12px rgba(0, 0, 0, 0.1);
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  text-align: center;
  color: #666;
}

@media (max-width: 768px) {
  .nav-content {
    flex-direction: column;
    height: auto;
    padding: 15px 20px;
  }

  .nav-links {
    margin-top: 15px;
    gap: 15px;
  }
}
</style>
