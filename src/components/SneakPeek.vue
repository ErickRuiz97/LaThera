<template>
  <section class="espacio-adelanto py-5">
    <div class="container">
      <h2 class="text-center mb-3">Sneak-Peek <span class="text-secondary">at the </span><span class="text-priimary">Space</span></h2>
      <p class="text-center mb-5 lead">
        Picture airy rooms with plants, calming sage walls, and modern furniture<br>
        ready for your next breakthrough session
      </p>

      <div class="row g-3">
        <div class="col-12 col-md-6">
          <img src="@/assets/images/Gallery/3.png" style="max-height: 500px;" class="img-fluid rounded" alt="Habitación espaciosa con plantas y pared salvia">
        </div>
        <div class="col-12 col-md-6">
          <div class="row g-3">
            <div class="col-12 col-sm-6">
              <img src="@/assets/images/Gallery/4.png" class="img-fluid rounded" alt="Habitación minimalista con planta">
            </div>
            <div class="col-12 col-sm-6">
              <img src="@/assets/images/Gallery/5.png" class="img-fluid rounded" alt="Sala de estar con sofá marrón y estanterías verdes">
            </div>
            <div class="col-7">
              <img src="@/assets/images/Gallery/1.png" class="img-fluid rounded" alt="Zona de salón moderna">
            </div>
            <div class="col-5">
              <img src="@/assets/images/Gallery/2.png" class="img-fluid rounded" alt="Sala de estar con pared verde y obras de arte">
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'EspacioAdelanto',
};
</script>

<style scoped>
.espacio-adelanto {
  background-color: #f8f7f3;
}

.espacio-adelanto h2 {
  font-size: 2.5rem;
  font-weight: 600;
  color: #333;
}

.espacio-adelanto h2 .text-primary {
  color: #8c9e82 !important;
}
.text-secondary {
  color: #D2B8A3 !important;
}

.espacio-adelanto p.lead {
  color: #555;
  font-size: 1.15rem;
}

.espacio-adelanto img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}
</style>
