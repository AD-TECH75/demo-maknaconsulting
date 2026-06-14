<script setup>
// Services page component: manages featured services, searchable service list, and highlight rendering.
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { allServices } from '@/data/services/ServiceData'
import HighlightedServices from '@/components/services/HighlightedServices.vue'

import img1 from '@/assets/services/hero/1.png'
import img2 from '@/assets/services/hero/2.png'
import img3 from '@/assets/services/hero/3.png'
const images = [img1, img2, img3]
const currentImage = ref(0)
let interval = null
onMounted(() => {
  interval = setInterval(() => {
    currentImage.value = (currentImage.value + 1) % images.length
  }, 2000)
})
onUnmounted(() => {
  clearInterval(interval)
})


const search = ref('')
const filteredServices = computed(() => {
  if (!search.value) return allServices

  return allServices.filter((service) =>
    (service.title + ' ' + service.description).toLowerCase().includes(search.value.toLowerCase()),
  )
})

const highlightText = (text) => {
  if (!search.value) return text

  const regex = new RegExp(`(${search.value})`, 'gi')

  return text.replace(regex, `<mark>$1</mark>`)
}
</script>

<template>
  <div class="service-page">
    <!-- Hero section with background image and overlay -->
    <section class="position-relative vh-100 overflow-hidden" data-aos="zoom-in">
      <!-- Background image layer -->
      <img
        :key="currentImage"
        :src="images[currentImage]"
        alt="Hero Background"
        class="position-absolute top-0 start-0 w-100 h-100 object-fit-cover"
      />

      <!-- Dark overlay for contrast -->
      <div class="position-absolute top-0 start-0 w-100 h-100 bg-dark opacity-75"></div>

      <!-- Hero content centered in the viewport -->
      <div
        class="container position-absolute top-50 start-50 translate-middle text-center text-white"
      >
        <span class="badge bg-warning text-dark px-3 py-2 mb-3"> Makna Consulting </span>

        <h1 class="display-3 fw-bold mb-4">Layanan Kami</h1>

        <p class="lead col-lg-8 mx-auto text-light">
          "Kami menyediakan berbagai layanan konsultasi strategis dan solusi bisnis terintegrasi
          yang dirancang khusus untuk mendorong pertumbuhan serta efisiensi operasional organisasi
          Anda."
        </p>
      </div>
    </section>

    <HighlightedServices />

    <!-- Search input section -->
    <section class="container" data-aos="flip-right">
      <div class="search-wrapper">
        <i class="bi bi-search"></i>

        <input v-model="search" class="form-control" placeholder="Cari layanan..." />
      </div>
    </section>

    <!-- All services listing section -->
    <section class="container py-5 allServices">
      <div class="d-flex justify-content-between mb-4" data-aos="zoom-in-up">
        <h2 class="fw-bold">Semua Layanan</h2>

        <span class="badge bg-warning text-dark">
          {{ filteredServices.length }}
        </span>
      </div>

      <div class="row g-4">
        <div
          class="col-md-6 col-lg-4"
          v-for="(service, i) in filteredServices"
          :key="i"
          data-aos="zoom-in-up"
        >
          <div class="card h-100 service-card border-0">
            <div class="card-body">
              <h5 class="fw-bold" v-html="highlightText(service.title)" />

              <p class="text-muted" v-html="highlightText(service.description)" />
            </div>
          </div>
        </div>
      </div>

      <div v-if="filteredServices.length === 0" class="text-center py-5">
        <h5>No results found</h5>

        <p class="text-muted">Try a different search term</p>
      </div>
    </section>
  </div>
</template>

<style scoped>
.allServices {
  background-color: #ffffff;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 2000 1500'%3E%3Cdefs%3E%3Crect stroke='%23FFFFFF' stroke-width='0.3' width='1' height='1' id='s'/%3E%3Cpattern id='a' width='3' height='3' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cuse fill='%23fcfcfc' href='%23s' y='2'/%3E%3Cuse fill='%23fcfcfc' href='%23s' x='1' y='2'/%3E%3Cuse fill='%23fafafa' href='%23s' x='2' y='2'/%3E%3Cuse fill='%23fafafa' href='%23s'/%3E%3Cuse fill='%23f7f7f7' href='%23s' x='2'/%3E%3Cuse fill='%23f7f7f7' href='%23s' x='1' y='1'/%3E%3C/pattern%3E%3Cpattern id='b' width='7' height='11' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23f5f5f5'%3E%3Cuse href='%23s'/%3E%3Cuse href='%23s' y='5' /%3E%3Cuse href='%23s' x='1' y='10'/%3E%3Cuse href='%23s' x='2' y='1'/%3E%3Cuse href='%23s' x='2' y='4'/%3E%3Cuse href='%23s' x='3' y='8'/%3E%3Cuse href='%23s' x='4' y='3'/%3E%3Cuse href='%23s' x='4' y='7'/%3E%3Cuse href='%23s' x='5' y='2'/%3E%3Cuse href='%23s' x='5' y='6'/%3E%3Cuse href='%23s' x='6' y='9'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='h' width='5' height='13' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23f5f5f5'%3E%3Cuse href='%23s' y='5'/%3E%3Cuse href='%23s' y='8'/%3E%3Cuse href='%23s' x='1' y='1'/%3E%3Cuse href='%23s' x='1' y='9'/%3E%3Cuse href='%23s' x='1' y='12'/%3E%3Cuse href='%23s' x='2'/%3E%3Cuse href='%23s' x='2' y='4'/%3E%3Cuse href='%23s' x='3' y='2'/%3E%3Cuse href='%23s' x='3' y='6'/%3E%3Cuse href='%23s' x='3' y='11'/%3E%3Cuse href='%23s' x='4' y='3'/%3E%3Cuse href='%23s' x='4' y='7'/%3E%3Cuse href='%23s' x='4' y='10'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='c' width='17' height='13' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23f2f2f2'%3E%3Cuse href='%23s' y='11'/%3E%3Cuse href='%23s' x='2' y='9'/%3E%3Cuse href='%23s' x='5' y='12'/%3E%3Cuse href='%23s' x='9' y='4'/%3E%3Cuse href='%23s' x='12' y='1'/%3E%3Cuse href='%23s' x='16' y='6'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='d' width='19' height='17' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23FFFFFF'%3E%3Cuse href='%23s' y='9'/%3E%3Cuse href='%23s' x='16' y='5'/%3E%3Cuse href='%23s' x='14' y='2'/%3E%3Cuse href='%23s' x='11' y='11'/%3E%3Cuse href='%23s' x='6' y='14'/%3E%3C/g%3E%3Cg fill='%23efefef'%3E%3Cuse href='%23s' x='3' y='13'/%3E%3Cuse href='%23s' x='9' y='7'/%3E%3Cuse href='%23s' x='13' y='10'/%3E%3Cuse href='%23s' x='15' y='4'/%3E%3Cuse href='%23s' x='18' y='1'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='e' width='47' height='53' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23FFC107'%3E%3Cuse href='%23s' x='2' y='5'/%3E%3Cuse href='%23s' x='16' y='38'/%3E%3Cuse href='%23s' x='46' y='42'/%3E%3Cuse href='%23s' x='29' y='20'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='f' width='59' height='71' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23FFC107'%3E%3Cuse href='%23s' x='33' y='13'/%3E%3Cuse href='%23s' x='27' y='54'/%3E%3Cuse href='%23s' x='55' y='55'/%3E%3C/g%3E%3C/pattern%3E%3Cpattern id='g' width='139' height='97' patternUnits='userSpaceOnUse' patternTransform='scale(50) translate(-980 -735)'%3E%3Cg fill='%23FFC107'%3E%3Cuse href='%23s' x='11' y='8'/%3E%3Cuse href='%23s' x='51' y='13'/%3E%3Cuse href='%23s' x='17' y='73'/%3E%3Cuse href='%23s' x='99' y='57'/%3E%3C/g%3E%3C/pattern%3E%3C/defs%3E%3Crect fill='url(%23a)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23b)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23h)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23c)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23d)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23e)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23f)' width='100%25' height='100%25'/%3E%3Crect fill='url(%23g)' width='100%25' height='100%25'/%3E%3C/svg%3E");
  background-attachment: fixed;
  background-size: cover;
}
.service-page {
  background: #fff;
}

.service-hero-section {
  background: linear-gradient(135deg, #fff, #fff7db);
}

.highlight-card {
  overflow: hidden;
  border-radius: 25px;
  transition: 0.3s;
}

.highlight-card img {
  height: 220px;
  object-fit: cover;
}

.highlight-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
}

.search-wrapper {
  position: relative;
  max-width: 700px;
  margin: auto;
}

.search-wrapper i {
  position: absolute;
  left: 20px;
  top: 50%;
  transform: translateY(-50%);
  z-index: 2;
}

.search-wrapper input {
  padding-left: 50px;
  height: 55px;
  border-radius: 50px;
  border: none;
  background: #f5f5f5;
}

.search-wrapper input:focus {
  box-shadow: none;
  background: white;
  border: 1px solid #ffc107;
}

.service-card {
  border-radius: 20px;
  transition: 0.3s;
}

.service-card:hover {
  transform: translateY(-5px);

  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.07);
}

:deep(mark) {
  background: #ffe96e;
  padding: 2px 4px;
  border-radius: 6px;
}
</style>
