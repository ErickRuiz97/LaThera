<template>
  <section class="callout-section d-flex">
    <div class="container" style="min-height: 100% !important">
      <div class="row h-100">
        <div class="col-md-5 h-100 bg-overlay">
          <div class="p-4 d-flex flex-column justify-content-center w-50">
            <div class="d-flex justify-content-center mb-3">
              <img src="@/assets/icon-set/Lathera Icons-07.svg" alt="Heart Icon" width="48" />
            </div>
            <div class="mb-3">
              <p class="mb-1 fw-semibold">Calm, fully furnished suites in the heart of the city.</p>
              <p class="mb-0 small">Zero leases, simple online booking, and a built-in directory that connects you with
                new clients.</p>
            </div>
            <button class="btn btn-outline-light mt-3 align-self-start">Join the Launch List</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>


<style scoped>
.callout-section {
  background: url('@/assets/images/Sub headline.png') center center / cover no-repeat;
  min-height: 520px;
  color: white;
}

@media (max-width: 768px) {
  .callout-section {
    background-position: 70% center !important;
  }
}

.bg-overlay {
  background-color: rgba(137, 150, 129, 0.5);
  color: white;
  backdrop-filter: blur(2px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}
</style>
