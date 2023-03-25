<script setup>
import data from "../assets/data.json";
</script>

<template>
  <div class="container">
    <div
      v-for="{ category, description, icon } in data"
      :class="`card card-${category}`"
    >
      <img
        class="card-icon"
        :src="`${icon}`"
        width="80"
        height="80"
        alt=""
        aria-hidden="true"
      />
      <div class="card-description">
        <h1 class="card-title">{{ category }}</h1>
        <p :class="`card-${description}`">
          {{ description }}
        </p>
      </div>
      <div class="btn-link">
        <a :class="` btn btn-${category}`" href="#">Learn More</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
img {
  /* width: 100%; */
  height: auto;
}
.container {
  padding: 5.3rem 1.5rem;
}

.card {
  padding: 3.5rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-sedans {
  background-color: var(--bright-orange);
  border-radius: 0.5rem 0.5rem 0 0;
}

.card-suvs {
  background-color: var(--dark-cyan);
}

.card-luxury {
  background-color: var(--very-dark-cyan);
  border-radius: 0 0 0.5rem 0.5rem;
}

.card-title {
  font-family: "Big Shoulders Display", cursive;
  text-transform: uppercase;
  font-weight: 700;
  font-size: 2.5rem;
  color: var(--very-light-gray);
  padding: 1rem 0;
}

.card-description {
  line-height: 1.5rem;
  color: var(--transparent-white);
}

.btn {
  font-family: "Lexend Deca", sans-serif;
  text-decoration: none;
  padding: 0.9rem 2rem;
  border-radius: 5rem;
  background-color: var(--very-light-gray);
  border: none;
}

.btn-link {
  padding: 3rem 0;
}

.btn-sedans {
  color: var(--bright-orange);
}

.btn-suvs {
  color: var(--dark-cyan);
}

.btn-luxury {
  color: var(--very-dark-cyan);
}

.btn:hover {
  background: none;
  border: 3px solid var(--very-light-gray);
  color: var(--very-light-gray);
}

@media (width >=1440px) {
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .container {
    display: flex;
  }

  .card {
    width: 18.75rem;
  }

  .card-description {
    padding-bottom: 5rem;
  }

  .card-sedans {
    border-radius: 0.5rem 0 0 0.5rem;
  }

  .card-luxury {
    border-radius: 0 0.5rem 0.5rem 0;
  }
}
</style>
