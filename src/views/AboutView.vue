<template>
  <div class="about">
    <div class="about-header">
      <div class="profile-card">
        <div class="avatar-container">
          <img src="https://placedog.net/500" alt="萨摩耶头像" class="avatar">
        </div>
        <h1 class="name">早上爬不起</h1>
        <p class="motto">"做有趣的人，干有趣的事"</p>
        <div class="social-links">
          <a href="mailto:1458621583@qq.com" class="social-link">
            <i class="fas fa-envelope"></i>
          </a>
          <a href="https://github.com/sq-lai" target="_blank" class="social-link">
            <i class="fab fa-github"></i>
          </a>
          <a href="https://www.zhihu.com/people/xi-xi-43-51-79" target="_blank" class="social-link zhihu-link">
            知
          </a>
        </div>
      </div>
    </div>

    <div class="about-content">
      <section class="about-section">
        <h2 class="section-title">
          <i class="fas fa-user-circle"></i>
          个人简介
        </h2>
        <div class="section-content">
          <p>大家好，欢迎来到我的博客世界！我硕士就读于东南大学电子信息专业，具备前后端项目开发能力，熟练掌握单体项目开发，对微服务项目有一定的基础与认知。技术栈主要集中在后端开发领域，熟悉掌握常用中间件。喜欢探索研究有意思的技术，有一定思维发散能力！</p>
          <p>目前主要探索Java与大语言模型的结合应用，致力于将AI能力集成到企业级应用中，实现智能化的业务处理和决策支持。</p>
        </div>
      </section>

      <section class="about-section">
        <h2 class="section-title">
          <i class="fas fa-laptop-code"></i>
          技术栈
        </h2>
        <div class="section-content">
          <div class="skills-container">
            <div class="skill-category">
              <h3><i class="fas fa-code"></i> 编程语言</h3>
              <div class="skill-list">
                <div class="skill-item">
                  <span class="skill-name">Java</span>
                  <div class="skill-bar">
                    <div class="skill-progress" style="width: 95%">
                      <span class="skill-percentage">95%</span>
                    </div>
                  </div>
                </div>
                <div class="skill-item">
                  <span class="skill-name">Python</span>
                  <div class="skill-bar">
                    <div class="skill-progress" style="width: 80%">
                      <span class="skill-percentage">80%</span>
                    </div>
                  </div>
                </div>
                <div class="skill-item">
                  <span class="skill-name">C/C++</span>
                  <div class="skill-bar">
                    <div class="skill-progress" style="width: 70%">
                      <span class="skill-percentage">70%</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="skill-category">
              <h3><i class="fas fa-cloud"></i> 微服务 & 框架</h3>
              <div class="tech-tags">
                <span class="tech-tag">Spring Boot</span>
                <span class="tech-tag">Spring Cloud</span>
                <span class="tech-tag">MyBatis Plus</span>
                <span class="tech-tag">Vue</span>
                <span class="tech-tag">ElementUI</span>
              </div>
            </div>

            <div class="skill-category">
              <h3><i class="fas fa-database"></i> 数据库 & 中间件</h3>
              <div class="tech-tags">
                <span class="tech-tag">MySQL</span>
                <span class="tech-tag">Redis</span>
                <span class="tech-tag">MongoDB</span>
                <span class="tech-tag">RabbitMQ</span>
                <span class="tech-tag">Seata</span>

              </div>
            </div>

            <div class="skill-category">
              <h3><i class="fas fa-tools"></i> 工具 & 平台</h3>
              <div class="tech-tags">
                <span class="tech-tag">Docker</span>
                <span class="tech-tag">Git</span>
                <span class="tech-tag">XXL-Job</span>
                <span class="tech-tag">Drools</span>
                <span class="tech-tag">MinIO</span>
                <span class="tech-tag">阿里云IoT</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="about-section">
        <h2 class="section-title">
          <i class="fas fa-award"></i>
          Honors & Awards
        </h2>
        <div class="section-content">
          <div class="certifications">
            <div class="cert-item">
              <i class="fas fa-trophy"></i>
              <span>Third Prize in China Undergraduate Mathematical Contest in Modeling (HuaShu Cup)</span>
            </div>
            <div class="cert-item">
              <i class="fas fa-trophy"></i>
              <span>Third Prize in China Undergraduate Mathematical Contest in Modeling (CUMCM)</span>
            </div>
            <div class="cert-item">
              <i class="fas fa-certificate"></i>
              <span>Second-Class Scholarship at Southeast University</span>
            </div>
            <div class="cert-item">
              <i class="fas fa-medal"></i>
              <span>Outstanding Volunteer of 2024 Nanjing Half Marathon</span>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.about {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.about-header {
  margin-bottom: 40px;
}

.profile-card {
  background: linear-gradient(135deg, #1e88e5 0%, #42a5f5 100%);
  border-radius: 16px;
  padding: 40px;
  text-align: center;
  color: white;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.avatar-container {
  width: 150px;
  height: 150px;
  margin: 0 auto 20px;
  border-radius: 50%;
  padding: 5px;
  background: rgba(255, 255, 255, 0.2);
}

.avatar {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}

.name {
  font-size: 2em;
  margin-bottom: 10px;
  font-weight: 600;
}

.motto {
  font-size: 1.2em;
  margin-bottom: 20px;
  opacity: 0.9;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.social-link {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-3px);
}

.about-content {
  display: grid;
  gap: 40px;
}

.about-section {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
}

.section-title {
  background: #f8f9fa;
  color: #2c3e50;
  padding: 20px;
  margin: 0;
  font-size: 1.5em;
  display: flex;
  align-items: center;
  gap: 10px;
}

.section-title i {
  color: #1e88e5;
}

.section-content {
  padding: 30px;
}

.section-content p {
  color: #666;
  line-height: 1.8;
  margin-bottom: 15px;
}

.skills-container {
  display: grid;
  gap: 30px;
}

.skill-category h3 {
  color: #2c3e50;
  margin-bottom: 20px;
  font-size: 1.2em;
  display: flex;
  align-items: center;
  gap: 10px;
}

.skill-category h3 i {
  color: #1e88e5;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 20px;
}

.tech-tag {
  background: linear-gradient(135deg, #1e88e5 0%, #42a5f5 100%);
  color: white;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9em;
  transition: all 0.3s ease;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.tech-tag:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.skill-list {
  margin-bottom: 20px;
}

.skill-item {
  display: grid;
  gap: 8px;
}

.skill-name {
  color: #666;
  font-size: 0.9em;
}

.skill-bar {
  height: 8px;
  background: #f0f0f0;
  border-radius: 4px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background: linear-gradient(90deg, #1e88e5 0%, #42a5f5 100%);
  border-radius: 4px;
  position: relative;
  transition: width 1s ease-in-out;
}

.skill-percentage {
  position: absolute;
  right: 0;
  top: -25px;
  font-size: 0.8em;
  color: #666;
}

.certifications {
  display: grid;
  gap: 20px;
}

.cert-item {
  display: flex;
  align-items: center;
  gap: 15px;
  color: #666;
  padding: 15px;
  background: #f8f9fa;
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.cert-item:hover {
  transform: translateX(10px);
}

.cert-item i {
  color: #1e88e5;
  font-size: 1.2em;
}

.zhihu-link {
  font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Microsoft YaHei", sans-serif;
  font-weight: bold;
  font-size: 1.2em;
}

@media (max-width: 768px) {
  .about {
    padding: 20px;
  }

  .profile-card {
    padding: 30px 20px;
  }

  .avatar-container {
    width: 120px;
    height: 120px;
  }

  .name {
    font-size: 1.5em;
  }

  .motto {
    font-size: 1em;
  }

  .section-content {
    padding: 20px;
  }
}
</style>
