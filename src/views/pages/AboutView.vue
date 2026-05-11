<template>
  <div>
    <!-- ========================= -->
    <!-- HERO SECTION -->
    <!-- ========================= -->
    <section class="hero-section bg-warning text-dark text-center py-5">
      <div class="container">
        <h1 class="fw-bold">Makna Consulting</h1>
        <p class="lead">Meningkatkan kapasitas SDM & tata kelola organisasi secara profesional</p>
      </div>
    </section>

    <!-- ========================= -->
    <!-- ABOUT SECTION -->
    <!-- ========================= -->
    <section class="about-section py-5">
      <div class="container">
        <!-- Tentang Kami -->
        <div class="row align-items-center mb-5">
          <div class="col-md-6">
            <img src="https://placehold.co/500x300" class="img-fluid rounded" />
          </div>
          <div class="col-md-6">
            <h2>Tentang Kami</h2>
            <p>
              Makna Consulting merupakan bagian dari CV. Mapah Karya Natar yang bergerak di bidang
              pengembangan SDM, manajemen pemerintahan, serta penyelenggaraan pelatihan dan event.
            </p>
          </div>
        </div>

        <!-- Latar Belakang -->
        <div class="row align-items-center mb-5 flex-md-row-reverse">
          <div class="col-md-6">
            <img src="https://placehold.co/500x300" class="img-fluid rounded" />
          </div>
          <div class="col-md-6">
            <h2>Latar Belakang</h2>
            <p>
              Perusahaan ini terbentuk dari kebutuhan peningkatan kualitas pelayanan publik dan
              kapasitas SDM di berbagai instansi dan organisasi.
            </p>
          </div>
        </div>

        <!-- Motivasi -->
        <div class="row align-items-center mb-5">
          <div class="col-md-6">
            <img src="https://placehold.co/500x300" class="img-fluid rounded" />
          </div>
          <div class="col-md-6">
            <h2>Motivasi Kami</h2>
            <p>
              Kami berkomitmen membantu organisasi berkembang melalui pelatihan dan konsultasi yang
              berdampak nyata.
            </p>
          </div>
        </div>

        <!-- Nilai & Filosofi -->
        <div class="row align-items-center flex-md-row-reverse">
          <div class="col-md-6">
            <img src="https://placehold.co/500x300" class="img-fluid rounded" />
          </div>
          <div class="col-md-6">
            <h2>Nilai & Filosofi</h2>
            <ul>
              <li>Profesionalisme</li>
              <li>Integritas</li>
              <li>Kolaborasi</li>
              <li>Inovasi Berkelanjutan</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================= -->
    <!-- SERVICES SECTION -->
    <!-- ========================= -->
    <section class="services-section bg-light py-5">
      <div class="container">
        <h2 class="text-center mb-4">Layanan Utama</h2>

        <div class="row text-center">
          <div class="col-md-4">
            <div class="card p-3">
              <h5>Peningkatan SDM</h5>
              <p>Pelatihan, workshop, dan pengembangan kompetensi.</p>
            </div>
          </div>

          <div class="col-md-4">
            <div class="card p-3">
              <h5>Manajemen Pemerintahan</h5>
              <p>Konsultasi SOP, ISO, dan reformasi birokrasi.</p>
            </div>
          </div>

          <div class="col-md-4">
            <div class="card p-3">
              <h5>Outbound & Event</h5>
              <p>Penyelenggaraan training, tour, dan team building.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================= -->
    <!-- TEAM SECTION -->
    <!-- ========================= -->
    <section class="team-section py-5">
      <div class="container">
        <h2 class="text-center mb-4">Tim & Kepemimpinan</h2>

        <div class="row text-center">
          <div class="col-md-4">
            <div class="card p-3">
              <img src="https://placehold.co/150" class="rounded-circle mx-auto mb-3" />
              <h5>Nama Pemimpin</h5>
              <p>Direktur</p>
            </div>
          </div>

          <div class="col-md-4">
            <div class="card p-3">
              <img src="https://placehold.co/150" class="rounded-circle mx-auto mb-3" />
              <h5>Nama Tim</h5>
              <p>Trainer Senior</p>
            </div>
          </div>

          <div class="col-md-4">
            <div class="card p-3">
              <img src="https://placehold.co/150" class="rounded-circle mx-auto mb-3" />
              <h5>Nama Tim</h5>
              <p>Consultant</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
   <!--
╔══════════════════════════════════════╗
║         CTA KE PAGE ABOUT           ║
╚══════════════════════════════════════╝
-->
  <section class="about-preview py-5 bg-white">
    <div class="container">
      <div class="row align-items-center">
        <!-- Sisi Kiri: Foto Tokoh/Tim dengan Aksen Design -->
        <div class="col-lg-5 mb-5 mb-lg-0">
          <div class="position-relative ps-4 pt-4">
            <!-- Aksen Kotak di Belakang Foto -->
            <div
              class="bg-primary position-absolute top-0 start-0 w-75 h-75 rounded-4"
              style="z-index: 0; opacity: 0.1"
            ></div>

            <img
              src="https://placehold.co/300x400"
              alt="CEO / Team Profile"
              class="img-fluid rounded-4 shadow-lg position-relative"
              style="z-index: 1"
            />

            <!-- Floating Badge Nama/Jabatan -->
            <div
              class="bg-white p-3 rounded-3 shadow-sm position-absolute bottom-0 start-0 mb-4 ms-n2"
              style="z-index: 2; min-width: 200px"
            >
              <h6 class="fw-bold mb-0">Bapak Nama Tokoh</h6>
              <small class="text-muted">CEO & Founder</small>
            </div>
          </div>
        </div>

        <!-- Sisi Kanan: Cerita Singkat -->
        <div class="col-lg-6 offset-lg-1">
          <span class="text-warning fw-bold text-uppercase ls-wide" style="letter-spacing: 2px"
            >Our Story</span
          >
          <h2 class="display-6 fw-bold mt-2 mb-4">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus, at?
          </h2>

          <p class="text-muted lead mb-4">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Odit ea ab suscipit dolorum.
            Tenetur, pariatur.
          </p>

          <p class="text-secondary mb-4">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore ut consequatur deleniti
            ducimus, exercitationem perspiciatis. Atque deleniti nemo accusantium adipisci
            consequatur deserunt cumque, quod id.
          </p>

          <!-- Button Arahkan ke AboutView.vue -->
          <div class="pt-2">
            <router-link to="/about" class="btn btn-outline-warning btn-lg px-4 rounded-pill">
              Kenali Kami Lebih Dekat <i class="bi bi-people ms-2"></i>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>






<style>
/* Card Styling */
.card {
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Image Behavior */
img {
  object-fit: cover;
}
</style>
