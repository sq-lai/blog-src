<template>
  <div class="home">
    <!-- 个人信息卡片 -->
    <div class="profile-card">
      <div class="avatar-container">
        <img src="https://placedog.net/500" alt="萨摩耶头像" class="avatar">
      </div>
      <h1 class="name">早上爬不起</h1>
      <p class="signature">"做有趣的人，干有趣的事"</p>
      <div class="social-stats">
        <div class="stat-item">
          <span class="number">128</span>
          <span class="label">文章</span>
        </div>
        <div class="stat-item">
          <span class="number">256</span>
          <span class="label">关注</span>
        </div>
        <div class="stat-item">
          <span class="number">512</span>
          <span class="label">粉丝</span>
        </div>
      </div>
    </div>

    <!-- 文章列表 -->
    <div class="article-list">
      <h2 class="section-title">最新文章</h2>
      <router-link 
        v-for="article in latestArticles" 
        :key="article.id" 
        :to="article.link"
        class="article-item">
        <div class="article-content">
          <h3 class="article-title">{{ article.title }}</h3>
          <p class="article-excerpt">{{ article.excerpt }}</p>
          <div class="article-meta">
            <span class="meta-item">
              <i class="far fa-calendar"></i>
              {{ article.date }}
            </span>
            <span class="meta-item">
              <i class="far fa-folder"></i>
              {{ article.category }}
            </span>
            <span class="meta-item">
              <i class="far fa-eye"></i>
              {{ article.readCount }} 阅读
            </span>
          </div>
        </div>
        <img v-if="article.coverImage" :src="article.coverImage" :alt="article.title" class="article-cover">
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  data() {
    return {
      latestArticles: [
        {
          id: 'spring-boot-3',
          title: 'Spring Boot 3.0新特性：性能提升与最佳实践',
          date: '2025-01-15',
          category: '后端开发',
          excerpt: '深入探讨Spring Boot 3.0的核心更新，包括原生镜像支持、AOT编译、Spring 6整合等重要特性，以及在企业级项目中的实践经验...',
          readCount: 328,
          coverImage: 'https://picsum.photos/800/600?random=1',
          link: '/article/spring-boot-3'
        },
        {
          id: 'microservice-evolution',
          title: '微服务架构实践：从单体到分布式系统的演进',
          date: '2025-01-13',
          category: '架构设计',
          excerpt: '基于实际项目经验，详细讲解微服务架构的设计原则、服务拆分策略、通信机制，以及常见问题的解决方案...',
          readCount: 256,
          coverImage: 'https://picsum.photos/800/600?random=2',
          link: '/article/microservice-evolution'
        },
        {
          id: 'mysql-optimization',
          title: 'MySQL性能优化实战指南',
          date: '2025-01-10',
          category: '数据库',
          excerpt: '深入分析MySQL索引原理、查询优化、事务管理，结合实际案例分享数据库性能调优的经验和方法...',
          readCount: 412,
          coverImage: 'https://picsum.photos/800/600?random=3',
          link: '/article/mysql-optimization'
        }
      ]
    }
  },
  methods: {
    goToArticle(id) {
      this.$router.push(`/article/${id}`)
    }
  }
}
</script>

<style scoped>
.home {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px;
  display: grid;
  grid-template-columns: 320px 1fr;
  gap: 60px;
  background-color: #f8f9fa;
}

.profile-card {
  background: white;
  border-radius: 16px;
  padding: 40px 30px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  position: sticky;
  top: 20px;
}

.avatar-container {
  width: 140px;
  height: 140px;
  margin: 0 auto 25px;
  border-radius: 50%;
  overflow: hidden;
  border: 4px solid #1e88e5;
  box-shadow: 0 4px 12px rgba(30, 136, 229, 0.2);
}

.avatar {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.name {
  color: #2c3e50;
  font-size: 26px;
  margin: 0 0 15px;
  font-weight: 600;
}

.signature {
  color: #666;
  font-size: 16px;
  margin: 0 0 30px;
  font-style: italic;
  line-height: 1.6;
}

.social-stats {
  display: flex;
  justify-content: space-around;
  padding-top: 25px;
  border-top: 1px solid #eee;
}

.stat-item {
  display: flex;
  flex-direction: column;
}

.number {
  color: #1e88e5;
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 5px;
}

.label {
  color: #666;
  font-size: 14px;
}

.article-list {
  background: white;
  border-radius: 16px;
  padding: 40px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
}

.section-title {
  color: #2c3e50;
  font-size: 26px;
  margin: 0 0 40px;
  padding-bottom: 20px;
  border-bottom: 2px solid #1e88e5;
  font-weight: 600;
}

.article-item {
  display: grid;
  grid-template-columns: 1fr 280px;
  gap: 30px;
  background: white;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 30px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  padding: 25px;
  text-decoration: none;
  color: inherit;
}

.article-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
}

.article-content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  flex: 1;
}

.article-title {
  color: #2c3e50;
  font-size: 22px;
  margin: 0 0 15px;
  font-weight: 600;
  line-height: 1.4;
}

.article-excerpt {
  color: #666;
  font-size: 15px;
  line-height: 1.8;
  margin: 0 0 20px;
}

.article-meta {
  display: flex;
  align-items: center;
  gap: 30px;
  color: #666;
  font-size: 14px;
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 8px;
  white-space: nowrap;
}

.meta-item i {
  color: #1e88e5;
  font-size: 16px;
  width: 16px;
  text-align: center;
}

.article-cover {
  width: 280px;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

@media (max-width: 1024px) {
  .home {
    padding: 30px;
    gap: 40px;
  }

  .article-item {
    grid-template-columns: 1fr 200px;
    padding: 20px;
  }

  .article-cover {
    width: 200px;
    height: 140px;
  }
}

@media (max-width: 768px) {
  .home {
    grid-template-columns: 1fr;
    padding: 20px;
  }
  
  .article-item {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .article-cover {
    width: 100%;
    height: 200px;
  }

  .profile-card {
    position: static;
    margin-bottom: 30px;
  }
}
</style>
