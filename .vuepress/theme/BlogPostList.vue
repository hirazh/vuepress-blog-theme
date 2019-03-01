<template>
    <div class="bloglist-container">
        <Header />
        <router-link class="router-link" v-for="(post, index) in posts" :key="index" :to="post.path">
            <div class="blogpost-card">
                <div class="blogpostcard-date">
                    {{post.frontmatter.date}}
                </div>
                <div class="blogpostcard-title">
                    <h1>{{post.frontmatter.title}}</h1>
                </div>
                <div class="blogpostcard-desc">
                    <p>{{post.frontmatter.description}}</p>
                </div>
                <div class="blogpostcard-author">
                    <p><span>Author: </span>{{post.frontmatter.author}}</p>
                </div>
            </div>
        </router-link>
        <Content />
    </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
    name: 'BlogPostList',
    components: { Header },
    computed: {
        posts() {
            return this.$site.pages
            .filter(x => x.path.startsWith('/blogs/'))
            .sort(
                (a, b) => new Date(b.frontmatter.date) - new Date(a.frontmatter.date)
            );
        }
    }
}
</script>

<style scoped>
.bloglist-container {
    margin-left: 20%;
    margin-right: 20%;
}

.router-link {
    text-decoration-line: none;
}

.blogpost-card {
    background-color: #332C40;
    color: #f0f0f0;
    margin-top: 8%;
    margin-bottom: 8%;
    padding: 4%;
    font-family: 'Open Sans', sans-serif;
}

.blogpostcard-title {
    font-family: 'Signika', sans-serif;
}

.blogpostcard-desc p {
    text-align: justify;
    line-height: 160%;
}

.blogpostcard-date, .blogpostcard-author {
    opacity: .5;
    font-style: italic;
    font-size: .8rem;
}

@media screen and (max-width: 750px) {
    .bloglist-container {
        margin-left: 8%;
        margin-right: 8%;
    }
    .blogpostcard-title {
        font-size: 1rem;
    }

    .blogpostcard-desc p {
        font-size: .9rem;
    }
}
</style>
