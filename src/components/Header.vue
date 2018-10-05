<template>
  <div class="container">
    <header class="blog-header py-3">
      <div class="row flex-nowrap justify-content-between align-items-center">
        <div class="col-4 pt-1">
          <a class="text-muted" href="#">Pushing news about technology.</a>
        </div>
        <div class="col-4 text-center">
          <a class="blog-header-logo text-dark" href="#">Tomorrow Headline</a>
        </div>
        <div class="col-4 d-flex justify-content-end align-items-center">
          <a class="text-muted" href="#">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor"
              stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mx-3">
              <circle cx="10.5" cy="10.5" r="7.5"></circle>
              <line x1="21" y1="21" x2="15.8" y2="15.8"></line>
            </svg>
          </a>
          <a class="btn btn-sm btn-outline-secondary" href="#">Sign up</a>
        </div>
      </div>
    </header>

    <div class="nav-scroller py-1 mb-2">
      <nav class="nav d-flex justify-content-between">
        <a v-for="tag in tags" :key="tag.slug" class="p-2 text-muted" :href="tag.slug">[[tag.name]]</a>
      </nav>
    </div>
  </div>
</template>

<script>
  import '../plugins/axios'

  export default {
    name: "THWebHeader",
    delimiters: ["[[", "]]"],
    data() {
      return {
        input: "",
        tags: {}
      };
    },
    methods: {
      getTags() {
        this.axios.get("api/news/tags/").then(
          response => this.tags = response.data
        ).catch(
          // eslint-disable-next-line
          error => console.error(error)
        )
      }
    },
    mounted() {
      this.getTags();
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .blog-header {
    line-height: 1;
    border-bottom: 1px solid #e5e5e5;
  }

  .blog-header-logo {
    font-family: "Playfair Display", Georgia, "Times New Roman", serif;
    font-size: 2.25rem;
  }

  .blog-header-logo:hover {
    text-decoration: none;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-family: "Playfair Display", Georgia, "Times New Roman", serif;
  }

  .display-4 {
    font-size: 2.5rem;
  }

  @media (min-width: 768px) {
    .display-4 {
      font-size: 3rem;
    }
  }

  .nav-scroller {
    position: relative;
    z-index: 2;
    height: 2.75rem;
    overflow-y: hidden;
  }

  .nav-scroller .nav {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: nowrap;
    flex-wrap: nowrap;
    padding-bottom: 1rem;
    margin-top: -1px;
    overflow-x: auto;
    text-align: center;
    white-space: nowrap;
    -webkit-overflow-scrolling: touch;
  }

  .nav-scroller .nav-link {
    padding-top: 0.75rem;
    padding-bottom: 0.75rem;
    font-size: 0.875rem;
  }

  .card-img-right {
    height: 100%;
    border-radius: 0 3px 3px 0;
  }

  .flex-auto {
    -ms-flex: 0 0 auto;
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

  /*
 * Blog name and description
 */
  .blog-title {
    margin-bottom: 0;
    font-size: 2rem;
    font-weight: 400;
  }

  .blog-description {
    font-size: 1.1rem;
    color: #999;
  }

  @media (min-width: 40em) {
    .blog-title {
      font-size: 3.5rem;
    }
  }

  /* Pagination */
  .blog-pagination {
    margin-bottom: 4rem;
  }

  .blog-pagination>.btn {
    border-radius: 2rem;
  }

  /*
 * Blog posts
 */
  .blog-post {
    margin-bottom: 4rem;
  }

  .blog-post-title {
    margin-bottom: 0.25rem;
    font-size: 2.5rem;
  }

  .blog-post-meta {
    margin-bottom: 1.25rem;
    color: #999;
  }

  /*
 * Footer
 */
  .blog-footer {
    padding: 2.5rem 0;
    color: #999;
    text-align: center;
    background-color: #f9f9f9;
    border-top: 0.05rem solid #e5e5e5;
  }

  .blog-footer p:last-child {
    margin-bottom: 0;
  }
</style>