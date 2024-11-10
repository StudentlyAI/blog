---
layout: home

hero:
  name: "StudentlyAI Blog"
  text: "Transform Your Academic Journey"
  tagline: "Discover expert insights, study strategies, and AI learning tools to excel in your studies."
  image:
    src: /hero-students-studying.jpg
    alt: Students collaborating with StudentlyAI
  actions:
    - theme: brand
      text: "Latest Posts"
      link: "#featured-posts"
    - theme: alt
      text: "Join Community"
      link: "/join"

features:
  - title: "Latest Articles"
    icon: 📝
    details: "How AI is Revolutionising University Study Habits"
    link: /blog/ai-study-habits
    date: "Nov 10, 2023"
    
  - title: "Study Tips"
    icon: 💡
    details: "5 Evidence-Based Revision Techniques for Better Retention"
    link: /blog/revision-techniques
    date: "Nov 8, 2023"
    
  - title: "Student Success"
    icon: 🎓
    details: "From C's to A's: A Student's Journey with AI-Assisted Learning"
    link: /blog/success-story
    date: "Nov 5, 2023"
    
  - title: "AI Tools"
    icon: 🤖
    details: "Maximising Your Study Sessions with AI Writing Assistance"
    link: /blog/ai-writing-tools
    date: "Nov 3, 2023"

head:
  - - meta
    - name: description
      content: "Explore the latest insights on AI-powered learning, study techniques, and academic success stories on the StudentlyAI blog."
  - - meta
    - name: keywords
      content: "StudentlyAI blog, study tips, AI learning, academic success, student resources"
  - - meta
    - property: "og:title"
      content: "StudentlyAI Blog - Transform Your Academic Journey"
  - - meta
    - property: "og:description"
      content: "Your source for expert academic insights, AI study tools, and learning strategies."

blog_categories:
  - title: "Study Techniques"
    link: /categories/study-techniques
  - title: "AI Tools"
    link: /categories/ai-tools
  - title: "Student Stories"
    link: /categories/student-stories
  - title: "Academic Tips"
    link: /categories/academic-tips
---

<script setup>
import { data as posts } from './posts.data.js'
</script>

<style>
:root {
  --vp-home-hero-name-color: transparent;
  --vp-home-hero-name-background: linear-gradient(120deg, #FF5F1F 30%, #FF8C00);
  --vp-button-brand-bg: #FF5F1F;
  --vp-button-brand-hover-bg: #FF8C00;
}

.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  padding: 2rem 0;
}

.blog-card {
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
  background: var(--vp-c-bg-soft);
}

.blog-card:hover {
  transform: translateY(-4px);
}

.post-meta {
  font-size: 0.9em;
  color: var(--vp-c-text-2);
}

.categories {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  margin: 2rem 0;
}

.category-tag {
  padding: 0.5rem 1rem;
  border-radius: 20px;
  background: var(--vp-c-bg-soft);
  color: var(--vp-c-text-1);
  text-decoration: none;
  transition: background 0.2s;
}

.category-tag:hover {
  background: var(--vp-c-brand);
  color: white;
}
</style>

<div class="container">
  <div class="categories">
    <a v-for="category in $frontmatter.blog_categories" 
       :key="category.title" 
       :href="category.link"
       class="category-tag">
      {{ category.title }}
    </a>
  </div>

  <div class="blog-grid">
    <div v-for="post in posts" 
         :key="post.url" 
         class="blog-card">
      <img :src="post.image" :alt="post.title">
      <div class="p-4">
        <h3>{{ post.title }}</h3>
        <p class="post-meta">{{ post.date }}</p>
        <p>{{ post.excerpt }}</p>
        <a :href="post.url" class="read-more">Read More →</a>
      </div>
    </div>
  </div>
</div>