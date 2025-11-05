---
layout: default
title: Baud的个人主页
description: Baud的个人网站 - 分享技术见解和生活思考
---

<div class="home-hero">
    <div class="container">
        <h1>欢迎来到我的个人网站</h1>
        <p>{{ site.description }}</p>
    </div>
</div>

<div class="container">
    <section class="home-section">
        <h2>👨💻 关于我</h2>
        <p>{{ site.author.bio }}</p>
        <p>目前专注于：</p>
        <ul>
            <li>Web 开发</li>
            <li>开源项目</li>
            <li>技术写作</li>
        </ul>
    </section>

    <section class="home-section">
        <h2>📝 最新文章</h2>
        <div class="posts-list">
            {% for post in site.posts limit: 3 %}
            <article class="post-card">
                <div class="post-card-header">
                    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
                    <div class="post-meta">
                        <time datetime="{{ post.date | date: '%Y-%m-%d' }}">
                            <i class="far fa-calendar"></i> {{ post.date | date: "%Y年%m月%d日" }}
                        </time>
                        {% if post.tags.size > 0 %}
                        <div class="post-tags">
                            {% for tag in post.tags limit: 3 %}
                            <a href="{{ '/tags/' | relative_url }}#{{ tag | slugify }}" class="tag">#{{ tag }}</a>
                            {% endfor %}
                        </div>
                        {% endif %}
                    </div>
                </div>
                <div class="post-card-content">
                    {% if post.excerpt %}
                    <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                    {% endif %}
                </div>
                <div class="post-card-footer">
                    <a href="{{ post.url | relative_url }}" class="read-more">阅读全文 <i class="fas fa-arrow-right"></i></a>
                </div>
            </article>
            {% endfor %}
        </div>
        <div style="text-align: center; margin-top: 2rem;">
            <a href="{{ '/blog/' | relative_url }}" class="read-more">查看所有文章 <i class="fas fa-arrow-right"></i></a>
        </div>
    </section>

    <section class="home-section">
        <h2>🔗 社交媒体</h2>
        <div class="social-links" style="justify-content: center; margin-top: 1rem;">
            <a href="{{ site.social_links.github }}" target="_blank" rel="noopener noreferrer" aria-label="GitHub">
                <i class="fab fa-github"></i>
            </a>
            <a href="{{ site.social_links.zhihu }}" target="_blank" rel="noopener noreferrer" aria-label="知乎">
                <i class="fab fa-zhihu"></i>
            </a>
            <a href="{{ site.social_links.csdn }}" target="_blank" rel="noopener noreferrer" aria-label="CSDN">
                <i class="fas fa-blog"></i>
            </a>
        </div>
    </section>
</div>

<style>
.home-section {
    margin-bottom: 3rem;
    padding: 2rem;
    background: var(--bg-light);
    border-radius: 8px;
}

.home-section h2 {
    color: var(--secondary-color);
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid var(--primary-color);
}

.home-section ul {
    margin-left: 2rem;
    margin-top: 0.5rem;
}
</style>
