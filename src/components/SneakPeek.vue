<template>
  <section class="espacio-adelanto py-5">
    <div class="container">
      <h2 class="text-center mb-3">
        Sneak-Peek <span class="text-secondary">at the </span><span class="text-priimary">Space</span>
      </h2>
      <p class="text-center mb-5 lead">
        Picture airy rooms with plants, calming sage walls, and modern furniture<br>
        ready for your next breakthrough session
      </p>

      <div class="row gx-4 gy-4">
        <div class="col-md-4">
          <img src="@/assets/images/Gallery/3.png" class="img-fluid h-100 rounded w-100 object-cover" alt="Habitación espaciosa con plantas y pared salvia">
        </div>

        <div class="col-md-8 d-grid gap-3 gallery-grid">
          <img src="@/assets/images/Gallery/4.png" class="img-fluid rounded w-100 h-100 object-cover img-4" alt="Habitación minimalista con planta">
          <img src="@/assets/images/Gallery/5.png" class="img-fluid rounded w-100 h-100 object-cover img-5" alt="Sala de estar con sofá marrón y estanterías verdes">
          <img src="@/assets/images/Gallery/1.png" class="img-fluid rounded w-100 h-100 object-cover" alt="Zona de salón moderna">
          <img src="@/assets/images/Gallery/2.png" class="img-fluid rounded w-100 h-100 object-cover" alt="Sala de estar con pared verde y obras de arte">
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
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 1rem;
}
.img-4 {
  grid-column: span 5;
}
.img-5 {
  grid-column: span 7;
}
.gallery-grid img:nth-child(3),
.gallery-grid img:nth-child(4) {
  grid-column: span 6;
}

.espacio-adelanto img.object-cover {
  object-fit: cover;
}

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

