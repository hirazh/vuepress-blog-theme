<template>
    <div class="postview-container">
        <div class="postTitle">
            <h1>{{ $page.frontmatter.title }}</h1>
            <p>
                <span class="poatDate">{{ $page.frontmatter.date }}</span>
                <span>|</span>
                <span class="postAuthor">Author: {{ $page.frontmatter.author }}</span>
            </p>
        </div>
        <Content class="content" />
    </div>
</template>

<script>
export default {
    name: 'PostView'
}
</script>

<style scoped>
.postview-container {
    margin-left: 20%;
    margin-right: 20%;
    color: #f0f0f0;
}
.postTitle {
    font-family: 'Signika', sans-serif;
    font-size: 2rem;
}
.postTitle p {
    margin-top: -5%;
}

.content {
    font-size: 1.5rem;
    font-family: 'Open Sans', sans-serif;
    text-align: justify;
    line-height: 160%;
}

.poatDate, .postAuthor, span {
    opacity: .5;
    font-style: italic;
    font-size: 1rem;
    margin-right: 1%;
}

@media screen and (max-width: 750px) {
    .postTitle h1{
        font-size: 2.2rem;
    }
    
    .postTitle span {
        font-size: .8rem;
    }

    .postTitle p {
        margin-top: -8%;
    }

    .content {
        font-size: 1rem;
    }

    .postview-container {
        margin-left: 8%;
        margin-right: 8%;
    }
}
</style>
