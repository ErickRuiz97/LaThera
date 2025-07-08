<template>
  <footer class="py-5 bg-white border-top">
    <div class="container">
      <div class="row position-relative align-items-start">
        <div class="col-md-6 text-center text-md-start mb-4 mb-md-0">
          <img src="@/assets/images/LaThera Logo.png" alt="LaThera Logo" class="mb-0 footer-logo-left" />
          <p class="small text-muted mb-0">
            LaThera Space provides flexible, contract-free <br />
            therapy suites and a curated therapist directory <br />
            that bridges professionals and the public.
          </p>
        </div>
        <div class="vertical-line d-none d-md-block"></div>
        <div class="col-md-5 text-md-start ms-md-4 d-flex align-items-start" style="margin-top: 50px;">
          <img src="@/assets/images/LaThera Logo.png" alt="LaThera Logo" class="footer-logo-right me-3" />
          <div>
            <p class="small text-muted mb-1"><strong>Our Mission:</strong></p>
            <h5 class="strong-primary mb-1">Foster growth, connection,</h5>
            <h5 class="strong-secondary mb-0">and well-being — one session a time.</h5>
          </div>
        </div>
      </div>

      <div class="row mt-4">
        <div class="col-12 text-center">
          <ul class="list-inline footer-menu">
            <li class="list-inline-item"><a href="#">For Professionals</a></li>
            <li class="list-inline-item"><a href="#">Find a Therapist</a></li>
            <li class="list-inline-item"><a href="#">About</a></li>
            <li class="list-inline-item"><a href="#">Blog</a></li>
            <li class="list-inline-item"><a href="#">Contact</a></li>
          </ul>
        </div>
      </div>
    </div>

    <div class="footer-line-full"></div>
  </footer>
</template>

<style scoped>
.strong-primary {
  color: #5a7263;
  font-size: 20px;
}

.strong-secondary {
  color: #d6b6a4;
  font-size: 20px;
}

.footer-logo-right {
  height: 100px;
  object-fit: contain;
  max-width: 100%;
}

.footer-logo-left {
  height: 140px;
  margin-top: -40px;
  object-fit: contain;
  max-width: 100%;
  margin-bottom: 0 !important;
}

.vertical-line {
  position: absolute;
  top: 60px;
  bottom: 0;
  left: 50%;
  width: 2px;
  background-color: #d6b6a4;
  transform: translateX(-50%) scaleX(0.15);
  transform-origin: center;
  z-index: 1;
}

.footer-menu {
  padding-left: 0;
  margin-bottom: 0;
  display: inline-block;
}

.footer-menu li {
  margin: 0 12px;
}

.footer-menu a {
  color: #5a7263;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 400;
}

.footer-menu a:hover {
  color: #3d5144;
}

.footer-line-full {
  width: 100%;
  height: 2px;
  background-color: #5a7263;
  margin-top: 1rem;
}

@media (max-width: 767.98px) {
  .vertical-line {
    display: none;
  }

  .col-md-6,
  .col-md-5 {
    text-align: center !important;
    margin-left: 0 !important;
  }

  .col-md-5.d-flex {
    flex-direction: column !important;
    align-items: center !important;
  }
}
</style>
