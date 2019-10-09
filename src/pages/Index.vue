<template>
  <Layout>
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <!--g-image alt="Example image" src="~/favicon.png" width="135" /-->

    <h1>Hello, world!</h1>

    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur excepturi labore tempore expedita, et iste tenetur suscipit explicabo! Dolores, aperiam non officia eos quod asperiores</p>
    <pre>{{ $page.posts.edges[0].node  }}</pre>

    <div v-for="({ node }) in $page.posts.edges" :key="node.id">
      <h2>{{ node.title }}</h2>
      <div v-html="node.content" />
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Hello, world!"
  }
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>

<page-query>
query {
  posts: allPost {
    edges {
      node {
        title
        content
      }
    }
  }
}
</page-query>
