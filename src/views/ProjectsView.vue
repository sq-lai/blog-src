<template>
  <div class="projects-container">
    <h1 class="page-title">项目展示</h1>
    <div class="projects-grid">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <img :src="project.image" :alt="project.name" class="project-image">
        <div class="project-content">
          <h3 class="project-title">{{ project.name }}</h3>
          <p class="project-description">{{ project.description }}</p>
          <div class="project-tech-stack">
            <span v-for="tech in project.techStack" :key="tech" class="tech-tag">
              {{ tech }}
            </span>
          </div>
          <div class="project-links">
            <a :href="project.github" target="_blank" class="project-link github">
              <i class="fab fa-github"></i> GitHub
            </a>
            <a v-if="project.demo" :href="project.demo" target="_blank" class="project-link demo">
              <i class="fas fa-external-link-alt"></i> Demo
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectsView',
  data() {
    return {
      projects: [
        {
          id: 1,
          name: '云途代驾',
          description: '基于B2B2C业务模式的代驾服务平台，包含订单管理、位置采集、司机管理、乘客管理、优惠统计、支付管理等核心功能。使用Spring Cloud微服务架构，整合Redis、MongoDB、RabbitMQ等中间件，实现高并发和分布式场景下的业务处理。',
          image: 'https://picsum.photos/400/300?random=1',
          techStack: ['Spring Cloud', 'MyBatis Plus', 'Redis', 'MongoDB', 'RabbitMQ', 'MinIO', 'Drools', 'Seata', 'XXL-Job', 'Docker'],
          features: [
            'Redis缓存用户信息和GEO位置搜索',
            'MongoDB实时位置上传和司乘同显',
            'RabbitMQ异步处理和订单超时取消',
            'MinIO分布式文件存储系统',
            'Redisson分布式锁和Seata分布式事务'
          ]
        },
        {
          id: 2,
          name: 'LabGuard实验室智能管理平台',
          description: '面向高校的实验室管理和实时监控平台，覆盖实验室管理、学生管理、传感器数据采集与监控、实时定位与报警等功能。采用Vue + Spring Boot架构，结合物联网技术实现智能化管理。',
          image: 'https://picsum.photos/400/300?random=2',
          techStack: ['Vue', 'ElementUI', 'Spring Boot', 'MyBatis Plus', 'Redis', 'Docker', '阿里云IoT', 'PyQt5'],
          features: [
            'Vue + ElementUI的前端界面设计',
            'Spring Boot + Redis的用户认证',
            'PyQt5环境监控界面开发',
            'MQTT协议和阿里云IoT集成',
            'Docker容器化部署'
          ],
          github: 'https://github.com/sq-lai/OrangePi/tree/main'
        },
        {
          id: 3,
          name: '技术学习笔记',
          description: '个人技术学习笔记整理与分享，包含后端开发、微服务架构、数据库、Docker容器化、Linux系统等多个技术领域的学习总结。通过双端共享的方式持续更新和完善，方便随时查阅和复习。',
          image: 'https://picsum.photos/400/300?random=3',
          techStack: ['Spring Cloud', 'Docker', 'Redis', 'Git', 'Linux', 'Drools'],
          features: [
            '后端开发技术栈学习笔记',
            '微服务架构实践总结',
            '数据库优化经验',
            'Docker容器化部署指南',
            'Linux系统使用技巧'
          ],
          github: 'https://github.com/sq-lai/notepad'
        }
      ]
    }
  }
}
</script>

<style scoped>
.projects-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.page-title {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 40px;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  padding: 20px;
}

.project-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.project-content {
  padding: 20px;
}

.project-title {
  color: #2c3e50;
  margin-bottom: 10px;
  font-size: 1.5em;
}

.project-description {
  color: #666;
  margin-bottom: 15px;
  line-height: 1.6;
}

.project-tech-stack {
  margin-bottom: 15px;
}

.tech-tag {
  display: inline-block;
  padding: 4px 8px;
  background: #e9ecef;
  color: #495057;
  border-radius: 4px;
  margin: 0 4px 4px 0;
  font-size: 0.9em;
}

.project-links {
  display: flex;
  gap: 10px;
}

.project-link {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border-radius: 4px;
  text-decoration: none;
  color: white;
  font-size: 0.9em;
  transition: background-color 0.3s ease;
}

.project-link i {
  margin-right: 5px;
}

.github {
  background-color: #24292e;
}

.github:hover {
  background-color: #1b1f23;
}

.demo {
  background-color: #42b983;
}

.demo:hover {
  background-color: #3aa876;
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style> 