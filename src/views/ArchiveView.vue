<template>
  <div class="archive-container">
    <h1 class="page-title">
      <i class="fas fa-archive"></i>
      文章归档
      <span class="article-count">共 {{ totalArticles }} 篇文章</span>
    </h1>
    <div class="timeline">
      <div v-for="year in archives" :key="year.year" class="year-section">
        <div class="year-header">
          <h2 class="year-title">
            <i class="far fa-calendar-alt"></i>
            {{ year.year }}
          </h2>
          <span class="year-count">{{ getYearArticleCount(year) }} 篇</span>
        </div>
        <div v-for="month in year.months" :key="month.month" class="month-section">
          <h3 class="month-title">
            <span class="month-dot"></span>
            {{ month.month }}月
          </h3>
          <ul class="article-list">
            <li v-for="article in month.articles" :key="article.id" class="article-item">
              <router-link :to="article.link" class="article-link">
                <div class="article-meta">
                  <span class="article-date">{{ article.date.split('-')[2] }}日</span>
                  <span class="article-category">{{ article.category }}</span>
                </div>
                <div class="article-main">
                  <h4 class="article-title">{{ article.title }}</h4>
                  <span class="article-stats">
                    <i class="fas fa-eye"></i> {{ article.readCount }}
                  </span>
                </div>
              </router-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ArchiveView',
  data() {
    return {
      archives: [
        {
          year: 2025,
          months: [
            {
              month: 1,
              articles: [
                {
                  id: 'spring-boot-3',
                  title: 'Spring Boot 3.0新特性：性能提升与最佳实践',
                  date: '2025-01-15',
                  category: '后端开发',
                  readCount: 328,
                  link: '/article/spring-boot-3'
                },
                {
                  id: 'microservice-evolution',
                  title: '微服务架构实践：从单体到分布式系统的演进',
                  date: '2025-01-13',
                  category: '架构设计',
                  readCount: 256,
                  link: '/article/microservice-evolution'
                },
                {
                  id: 'mysql-optimization',
                  title: 'MySQL性能优化实战指南',
                  date: '2025-01-10',
                  category: '数据库',
                  readCount: 412,
                  link: '/article/mysql-optimization'
                }
              ]
            }
          ]
        },
        {
          year: '2024',
          months: [
            {
              month: '12',
              articles: [
                {
                  id: 'spring-cloud-practice',
                  title: 'Spring Cloud微服务实践：从单体应用到分布式架构',
                  date: '2024-12-20',
                  category: '架构设计',
                  readCount: 358,
                  link: '/article/spring-cloud-practice'
                }
              ]
            },
            {
              month: '11',
              articles: [
                {
                  id: 'redis-optimization',
                  title: 'Redis性能优化实战：缓存设计与集群部署',
                  date: '2024-11-15',
                  category: '数据库',
                  readCount: 426,
                  link: '/article/redis-optimization'
                }
              ]
            },
            {
              month: '10',
              articles: [
                {
                  id: 'java-llm-integration',
                  title: 'Java与大语言模型的结合：智能化应用实践',
                  date: '2024-10-01',
                  category: 'AI应用',
                  readCount: 512,
                  link: '/article/java-llm-integration'
                }
              ]
            }
          ]
        }
      ]
    }
  },
  computed: {
    totalArticles() {
      return this.archives.reduce((total, year) => {
        return total + year.months.reduce((yearTotal, month) => {
          return yearTotal + month.articles.length
        }, 0)
      }, 0)
    }
  },
  methods: {
    getYearArticleCount(year) {
      return year.months.reduce((total, month) => {
        return total + month.articles.length
      }, 0)
    }
  }
}
</script>

<style scoped>
.archive-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 40px 20px;
}

.page-title {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 60px;
  font-size: 2em;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.page-title i {
  color: #1e88e5;
}

.article-count {
  font-size: 0.5em;
  color: #666;
  font-weight: normal;
  margin-left: 10px;
}

.timeline {
  position: relative;
  padding: 20px 0;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, #1e88e5 0%, #90caf9 100%);
}

.year-section {
  margin-bottom: 40px;
  position: relative;
}

.year-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
  background: white;
  padding: 10px 20px;
  border-radius: 30px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
}

.year-title {
  color: #2c3e50;
  font-size: 1.5em;
  margin: 0;
  display: flex;
  align-items: center;
  gap: 10px;
}

.year-title i {
  color: #1e88e5;
}

.year-count {
  color: #666;
  font-size: 0.9em;
  background: #f0f7ff;
  padding: 4px 12px;
  border-radius: 15px;
}

.month-section {
  margin-left: 30px;
  margin-bottom: 30px;
  position: relative;
}

.month-title {
  color: #1e88e5;
  font-size: 1.2em;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.month-dot {
  width: 12px;
  height: 12px;
  background: #1e88e5;
  border-radius: 50%;
  display: inline-block;
  margin-left: -36px;
  border: 2px solid white;
  box-shadow: 0 0 0 2px #1e88e5;
}

.article-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.article-item {
  margin-bottom: 15px;
  transition: all 0.3s ease;
}

.article-link {
  display: block;
  background: white;
  padding: 15px 20px;
  border-radius: 8px;
  text-decoration: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
}

.article-link:hover {
  transform: translateX(10px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.article-meta {
  display: flex;
  gap: 15px;
  margin-bottom: 8px;
}

.article-date {
  color: #666;
  font-size: 0.9em;
}

.article-category {
  color: #1e88e5;
  font-size: 0.9em;
  background: #f0f7ff;
  padding: 2px 8px;
  border-radius: 4px;
}

.article-main {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.article-title {
  color: #2c3e50;
  margin: 0;
  font-size: 1.1em;
  font-weight: 500;
}

.article-stats {
  color: #666;
  font-size: 0.9em;
  display: flex;
  align-items: center;
  gap: 5px;
}

@media (max-width: 768px) {
  .archive-container {
    padding: 20px;
  }

  .page-title {
    font-size: 1.5em;
    margin-bottom: 40px;
  }

  .year-header {
    padding: 8px 15px;
  }

  .year-title {
    font-size: 1.2em;
  }

  .month-section {
    margin-left: 20px;
  }

  .article-link:hover {
    transform: none;
  }
}
</style> 