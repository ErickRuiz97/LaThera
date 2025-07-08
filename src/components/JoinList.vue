<template>
  <section class="launch-section">
  <div class="section-rose text-white py-5 px-4 text-center text-md-start">
    <div class="container">
      <h2 class="mb-3">Join the Launch List</h2>
      <p>
        We’re opening doors in soon!<br />
        Drop your info below and be first in line for<br />
        tours, discounts, and exclusive events.
      </p>
    </div>
  </div>
  <div class="section-green-wrapper py-5 px-4 text-center text-md-start">
    <div class="section-green">
      <div class="container">
        <form class="form-wrapper">
          <input type="text" class="form-control mb-3" placeholder="Name" />
          <input type="email" class="form-control mb-3" placeholder="Email" />
          <input
            type="text"
            class="form-control mb-3"
            placeholder="Professional License / Interest"
          />
          <input
            type="text"
            class="form-control mb-4"
            placeholder="Preferred Move-In Date"
          />
          <button type="submit" class="btn btn-light mb-2 rounded-0 btn-green">Notify Me</button>
          <small class="text-white d-block">
            We respect your inbox and your privacy. No spam—ever.
          </small>
        </form>
      </div>
    </div>

    <img
      src="@/assets/images/Footer img.png"
      alt="Decor"
      class="footer-overlay"
    />
  </div>
  <img
    src="@/assets/images/Contact.png"
    alt="Contact"
    class="contact-overlay"
  />
</section>
</template>
<style scoped>
input{
  background-color: transparent;
}
input::placeholder {
  color: #fff;
  opacity: 1;
}
.btn-green {
  color: #8a9a88;
}
input:focus {
  background-color: transparent;
  box-shadow: none;
  border-color: #fff;
}
.launch-section {
  position: relative;
  width: 100%;
  background-color: #fefcf9;
  overflow: visible;
  margin: 0;
  padding: 0;
}

.contact-overlay {
  position: absolute;
  top: -30px;
  right: 0;
  max-width: 650px;
  height: auto;
  z-index: 10;
  pointer-events: none;
}

.section-rose {
  background-color: #d6b6a4;
  width: 100%;
}

.section-green-wrapper {
  background-color: #8a9a88;
  position: relative;
  overflow: visible;
  width: 100%;
}

.section-green {
  padding-bottom: 6rem;
  width: 100%;
}

.form-wrapper {
  max-width: 500px;
  position: relative;
  z-index: 1;
  margin-left: 0;
}

@media (max-width: 992px) {
  .form-wrapper {
    width: 100%;
    padding-right: 1rem;
  }
}

@media (max-width: 576px) {
  .form-wrapper {
    padding-left: 0.5rem;
    padding-right: 0.5rem;
  }
}

.footer-overlay {
  position: absolute;
  bottom: -120px;
  right: 2rem;
  max-width: 480px;
  z-index: 2;
  pointer-events: none;
}

@media (max-width: 992px) {
  .contact-overlay {
    max-width: 400px;
    top: -10px;
  }

  .footer-overlay {
    max-width: 300px;
    bottom: -80px;
  }

  .form-wrapper {
    max-width: 100%;
    padding: 0 1rem;
  }

  .section-green-wrapper,
  .section-green {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

@media (max-width: 576px) {
  .contact-overlay {
    display: none;
  }

  .footer-overlay {
    right: 1rem;
    max-width: 220px;
  }

  .form-wrapper input,
  .form-wrapper button {
    font-size: 0.9rem;
  }

  .section-rose p,
  .section-rose h2 {
    font-size: 1rem;
  }
}
</style>
