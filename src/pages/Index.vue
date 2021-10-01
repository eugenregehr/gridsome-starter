<template>
  <layout>
    <b-row>
      <b-col md="6">
        <h1>Startpage</h1>
        <p>
          Today, A lot of developers are conversant with the `alt` attribute on
          images. I can say most of us know that it is one way of making
          webpages accessible but do we really understand the scope of the
          alternative text, when to make use of it, how to use it. I agree it is
          one step to being an accessibility advocate so that is why in this
          article, I'll be explaining in detail the alt attribute and how
          practicing it can improve web accessibility in a long run.
        </p>
        <div></div>
      </b-col>
      <b-col md="6">
        <h1>Posts</h1>
        <b-card
          :title="post.node.title"
          v-for="post in $page.posts.edges"
          :key="post.node.id"
          class="mt-3"
        >
          <b-card-text> {{ post.node.description }} </b-card-text>
          <b-link :href="post.node.path">link</b-link>
        </b-card>
      </b-col>
    </b-row>
  </layout>
</template>

<page-query>
{
  posts: allPost {
    edges {
      node {
        title
        description
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Home",
  },
  data() {
    return {};
  },
};
</script>
