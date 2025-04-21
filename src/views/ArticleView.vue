<template>
  <div class="article-container" v-if="currentArticle">
    <article class="article">
      <header class="article-header">
        <h1 class="article-title">{{ currentArticle.title }}</h1>
        <div class="article-meta">
          <span class="meta-item">
            <i class="far fa-calendar"></i>
            {{ currentArticle.date }}
          </span>
          <span class="meta-item">
            <i class="far fa-folder"></i>
            {{ currentArticle.category }}
          </span>
          <span class="meta-item">
            <i class="far fa-eye"></i>
            {{ currentArticle.readCount }} 阅读
          </span>
        </div>
        <div class="article-tags">
          <span v-for="tag in currentArticle.tags" :key="tag" class="tag">
            <i class="fas fa-tag"></i>
            {{ tag }}
          </span>
        </div>
      </header>
      <div class="article-content" v-html="currentArticle.content"></div>
    </article>
  </div>
</template>

<script>
export default {
  name: 'ArticleView',
  data() {
    return {
      articles: {
        'spring-cloud-practice': {
          id: 'spring-cloud-practice',
          title: 'Spring Cloud微服务实践：从单体应用到分布式架构',
          date: '2024-12-20',
          category: '架构设计',
          readCount: 358,
          tags: ['Spring Cloud', '微服务', '分布式系统', '架构设计'],
          coverImage: 'https://picsum.photos/800/400?random=13',
          content: `
            <h1>1. 微服务架构概述</h1>
            <img src="https://picsum.photos/800/400?random=14" alt="微服务架构概述" class="article-image">
            <p>从单体应用到微服务架构的演进是一个渐进的过程，需要考虑以下几个关键方面：</p>
            <ul>
              <li>业务拆分原则与策略</li>
              <li>服务间通信机制的选择</li>
              <li>数据一致性的保证</li>
              <li>分布式事务的处理</li>
            </ul>

            <h2>2. Spring Cloud 核心组件</h2>
            <img src="https://picsum.photos/800/400?random=15" alt="Spring Cloud组件" class="article-image">
            <p>Spring Cloud提供了一站式的微服务解决方案：</p>
            <ul>
              <li>Nacos：服务注册与配置中心</li>
              <li>Gateway：API网关服务</li>
              <li>OpenFeign：声明式服务调用</li>
              <li>Sentinel：服务容错保护</li>
            </ul>

            <h2>3. 实践经验总结</h2>
            <img src="https://picsum.photos/800/400?random=16" alt="实践经验" class="article-image">
            <p>在实际项目中的最佳实践：</p>
            <ul>
              <li>合理的服务粒度控制</li>
              <li>统一的服务治理策略</li>
              <li>完善的监控告警机制</li>
              <li>灵活的扩展性设计</li>
            </ul>
          `
        },
        'redis-optimization': {
          id: 'redis-optimization',
          title: 'Redis性能优化实战：缓存设计与集群部署',
          date: '2024-11-15',
          category: '数据库',
          readCount: 426,
          tags: ['Redis', '性能优化', '缓存设计', '集群部署'],
          coverImage: 'https://picsum.photos/800/400?random=17',
          content: `
            <h1>1. 缓存更新策略</h1>
            <img src="https://picsum.photos/800/400?random=18" alt="缓存更新策略" class="article-image">
            <p>合理的缓存更新策略对于保证数据一致性至关重要：</p>
            <ul>
              <li>Cache Aside Pattern</li>
              <li>Write Through Pattern</li>
              <li>Write Behind Pattern</li>
              <li>延迟双删策略</li>
            </ul>

            <h2>2. 集群架构设计</h2>
            <img src="https://picsum.photos/800/400?random=19" alt="集群架构" class="article-image">
            <p>Redis集群的高可用方案：</p>
            <ul>
              <li>主从复制架构</li>
              <li>哨兵模式部署</li>
              <li>Cluster集群搭建</li>
              <li>数据分片策略</li>
            </ul>

            <h2>3. 性能优化实践</h2>
            <img src="https://picsum.photos/800/400?random=20" alt="性能优化" class="article-image">
            <p>Redis性能优化的关键点：</p>
            <ul>
              <li>内存管理优化</li>
              <li>网络延迟优化</li>
              <li>持久化策略优化</li>
              <li>慢查询优化</li>
            </ul>
          `
        },
        'java-llm-integration': {
          id: 'java-llm-integration',
          title: 'Java与大语言模型的结合：智能化应用实践',
          date: '2024-10-01',
          category: 'AI应用',
          readCount: 512,
          tags: ['Java', 'LLM', 'AI应用', '智能化'],
          coverImage: 'https://picsum.photos/800/400?random=21',
          content: `
            <h1>1. LLM集成方案</h1>
            <img src="https://picsum.photos/800/400?random=22" alt="LLM集成方案" class="article-image">
            <p>Java应用集成大语言模型的主要方案：</p>
            <ul>
              <li>OpenAI API集成</li>
              <li>本地模型部署</li>
              <li>混合部署方案</li>
              <li>自定义模型训练</li>
            </ul>

            <h2>2. 应用场景实践</h2>
            <img src="https://picsum.photos/800/400?random=23" alt="应用场景" class="article-image">
            <p>实际业务中的应用案例：</p>
            <ul>
              <li>智能客服系统</li>
              <li>代码智能补全</li>
              <li>文档自动生成</li>
              <li>数据分析报告</li>
            </ul>

            <h2>3. 性能与成本优化</h2>
            <img src="https://picsum.photos/800/400?random=24" alt="性能优化" class="article-image">
            <p>优化系统性能和控制成本的策略：</p>
            <ul>
              <li>请求限流控制</li>
              <li>结果缓存优化</li>
              <li>并发调用优化</li>
              <li>成本效益分析</li>
            </ul>
          `
        },
        'spring-boot-3': {
          id: 'spring-boot-3',
          title: 'Spring Boot 3.0新特性：性能提升与最佳实践',
          date: '2025-01-15',
          category: '后端开发',
          readCount: 328,
          tags: ['Spring Boot', 'Java', '性能优化', '企业实践'],
          coverImage: 'https://picsum.photos/800/400?random=1',
          content: `
            <h1>1. Spring Boot 3.0 核心更新</h1>
            <img src="https://picsum.photos/800/400?random=4" alt="Spring Boot 3.0核心特性" class="article-image">
            <p>Spring Boot 3.0带来了一系列重要更新，包括：</p>
            <ul>
              <li>基于Spring Framework 6.x构建</li>
              <li>支持Java 17+作为基准版本</li>
              <li>原生镜像支持，提供更快的启动速度</li>
              <li>AOT编译支持，改善应用性能</li>
            </ul>

            <h2>2. 性能优化亮点</h2>
            <img src="https://picsum.photos/800/400?random=5" alt="性能优化对比" class="article-image">
            <p>通过引入以下优化，显著提升了应用性能：</p>
            <ul>
              <li>启动时间减少高达50%</li>
              <li>内存占用降低30%</li>
              <li>请求处理延迟降低</li>
            </ul>

            <h2>3. 最佳实践建议</h2>
            <img src="https://picsum.photos/800/400?random=6" alt="最佳实践示例" class="article-image">
            <p>在企业实践中，我们总结了以下最佳实践：</p>
            <ul>
              <li>合理使用条件配置</li>
              <li>优化自动配置</li>
              <li>采用响应式编程模型</li>
            </ul>
          `
        },
        'microservice-evolution': {
          id: 'microservice-evolution',
          title: '微服务架构实践：从单体到分布式系统的演进',
          date: '2025-01-13',
          category: '架构设计',
          readCount: 256,
          tags: ['微服务', '分布式系统', 'Spring Cloud', '架构设计'],
          coverImage: 'https://picsum.photos/800/400?random=2',
          content: `
            <h1>1. 架构演进之路</h1>
            <img src="https://picsum.photos/800/400?random=7" alt="架构演进图" class="article-image">
            <p>从单体应用到微服务架构的演进过程中，我们经历了：</p>
            <ul>
              <li>单体应用的局限性分析</li>
              <li>服务拆分的策略和原则</li>
              <li>微服务架构的优势和挑战</li>
            </ul>

            <h2>2. Spring Cloud 实践</h2>
            <img src="https://picsum.photos/800/400?random=8" alt="Spring Cloud架构" class="article-image">
            <p>在实践中，我们采用了Spring Cloud全家桶：</p>
            <ul>
              <li>服务注册与发现</li>
              <li>配置中心</li>
              <li>服务网关</li>
              <li>负载均衡</li>
            </ul>

            <h2>3. 性能优化与监控</h2>
            <img src="https://picsum.photos/800/400?random=9" alt="性能监控" class="article-image">
            <p>为保证系统稳定性，我们建立了完善的监控体系：</p>
            <ul>
              <li>服务性能指标监控</li>
              <li>链路追踪</li>
              <li>日志聚合分析</li>
            </ul>
          `
        },
        'mysql-optimization': {
          id: 'mysql-optimization',
          title: 'MySQL性能优化实战指南',
          date: '2025-01-10',
          category: '数据库',
          readCount: 412,
          tags: ['MySQL', '性能优化', '数据库', '实战经验'],
          coverImage: 'https://picsum.photos/800/400?random=3',
          content: `
            <h1>1. 索引优化</h1>
            <img src="https://picsum.photos/800/400?random=10" alt="索引优化" class="article-image">
            <p>索引优化是提升MySQL性能的关键：</p>
            <ul>
              <li>合理设计索引结构</li>
              <li>避免索引失效的场景</li>
              <li>优化索引使用策略</li>
            </ul>

            <h2>2. 查询优化</h2>
            <img src="https://picsum.photos/800/400?random=11" alt="查询优化" class="article-image">
            <p>优化SQL查询性能的关键点：</p>
            <ul>
              <li>SQL语句优化</li>
              <li>执行计划分析</li>
              <li>Join策略优化</li>
            </ul>

            <h2>3. 性能监控</h2>
            <img src="https://picsum.photos/800/400?random=12" alt="性能监控" class="article-image">
            <p>建立完善的性能监控体系：</p>
            <ul>
              <li>慢查询日志分析</li>
              <li>性能指标监控</li>
              <li>资源使用率监控</li>
            </ul>
          `
        }
      }
    }
  },
  computed: {
    currentArticle() {
      const articleId = this.$route.params.id
      return this.articles[articleId]
    }
  }
}
</script>

<style scoped>
.article-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 20px;
}

.article {
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  padding: 30px;
}

.article-header {
  margin-bottom: 30px;
  text-align: center;
}

.article-title {
  color: #2c3e50;
  font-size: 2em;
  margin-bottom: 20px;
}

.article-meta {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 15px;
}

.meta-item {
  color: #666;
  display: flex;
  align-items: center;
  gap: 5px;
}

.article-tags {
  display: flex;
  justify-content: center;
  gap: 10px;
  flex-wrap: wrap;
}

.tag {
  background: #f0f7ff;
  color: #1e88e5;
  padding: 4px 12px;
  border-radius: 15px;
  font-size: 0.9em;
  display: flex;
  align-items: center;
  gap: 5px;
}

.article-content {
  line-height: 1.8;
  color: #2c3e50;
}

.article-section {
  margin-bottom: 30px;
}

.article-image {
  width: 100%;
  max-height: 400px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 20px;
}

.code-block {
  background: #f8f9fa;
  padding: 15px;
  border-radius: 6px;
  font-family: 'Courier New', Courier, monospace;
  overflow-x: auto;
  margin: 15px 0;
}

h2 {
  color: #1e88e5;
  margin: 30px 0 15px;
  font-size: 1.5em;
}

ul {
  padding-left: 20px;
  margin: 15px 0;
}

li {
  margin-bottom: 8px;
}

@media (max-width: 768px) {
  .article-container {
    padding: 20px;
  }

  .article {
    padding: 20px;
  }

  .article-title {
    font-size: 1.5em;
  }

  .article-meta {
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }
}
</style> 