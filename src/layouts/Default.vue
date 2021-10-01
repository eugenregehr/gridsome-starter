<template>
  <div class="container mt-3">
    <Header />
    <transition name="fade" appear>
      <main>
        <slot />
      </main>
    </transition>
    <Footer />
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>


<script>
import Header from "../components/Header";
import Footer from "../components/Footer";
export default {
  components: {
    Footer,
    Header,
  },
};
</script>

<style>
.fade-enter-active {
  transition: opacity 0.5s;
}

.fade-enter {
  opacity: 0;
}
</style>
