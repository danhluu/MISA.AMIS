<template>
  <div id="app">
    <Navbar />
    <Header />
    <Content />
  </div>
</template>

<script>
import Navbar from "@/components/layout/Navbar";
import Header from "@/components/layout/Header";
import Content from "@/components/layout/Content";
export default {
  name: 'App',
  components: {
   Navbar,
   Header,
   Content
  }
}
</script>

<style>
@import "./styles/main.css";


</style>
