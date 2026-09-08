<script setup>
import Navbar from "@/components/Navbar.vue";
import Hero from "@/sections/Hero.vue";
import About from "@/sections/About.vue";
import Activities from "@/sections/Activities.vue";
import Ministries from "@/sections/Ministries.vue";
import ContactSection from "@/sections/contact.vue";
import Footer from "@/components/Footer.vue";
</script>

<template>
  <div class="page">
    <Navbar />
    <main>
      <Hero />
      <About />
      <Activities />
      <Ministries />
      <ContactSection />
    </main>
    <Footer />
  </div>
</template>
