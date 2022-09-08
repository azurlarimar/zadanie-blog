<template>
  <div>
    <Header />
    <NuxtPage />
    <Footer />
  </div>
</template>

<script setup></script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&display=swap');
@import './node_modules/@vueform/toggle/themes/default.css';

:root {
  --border-colorful: #ff8a03;
  --border-light: #bebebe;
}

.blog-header {
  border-bottom: 1px solid #e5e5e5;
}

.blog-header-logo {
  font-family: 'Playfair Display', Georgia, 'Times New Roman', serif;
  font-size: 2.25rem;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: 'Playfair Display', Georgia, 'Times New Roman', serif;
}

.display-4 {
  font-size: 2.5rem;
}
@media (min-width: 768px) {
  .display-4 {
    font-size: 3rem;
  }
}

.flex-auto {
  flex: 0 0 auto;
}

.h-250 {
  height: 250px;
}
@media (min-width: 768px) {
  .h-md-250 {
    height: 250px;
  }
}

/* Pagination */
.blog-pagination {
  margin-bottom: 4rem;
}

/*
		 * Footer
		 */
.blog-footer {
  padding: 2.5rem 0;
  color: #727272;
  text-align: center;
}

.blog-footer p:last-child {
  margin-bottom: 0;
}

a {
  text-decoration: none;
}

a:hover {
  color: unset;
}

.content-wrap {
  width: 100%;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
}

.dark-mode body {
  background-color: #091a28;
  color: #ebf4f1;
}

.light-mode body {
  background-color: #ebf4f1;
  color: #091a28;
}

.dark-mode .blog-header-logo {
  color: #ebf4f1;
}

.light-mode .blog-header-logo {
  color: #091a28;
}

.light-mode .border-light {
  border-color: var(--border-light) !important;
}

.dark-mode .border-colorful {
  border-color: var(--border-colorful) !important;
}

.dark-mode .card-link {
  color: #ebf4f1;
}

.light-mode .card-link {
  color: #091a28;
}

.dark-mode .main-b-post {
  background-color: #ebf4f1;
  color: #091a28;
}

.light-mode .main-b-post {
  background-color: #091a28;
  color: #ebf4f1;
}

.b-highlight {
  color: #ff8a03;
}
</style>
