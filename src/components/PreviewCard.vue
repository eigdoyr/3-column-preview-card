<script setup>
import data from "../assets/data.json";
</script>

<template>
  <main>
    <div class="container">
      <div
        v-for="{ category, description, icon } in data"
        :class="`card card-${category}`"
      >
        <img
          class="card-icon"
          :src="`${icon}`"
          width="70"
          height="70"
          alt=""
          aria-hidden="true"
        />
        <div class="card-description">
          <h1 class="card-title">{{ category }}</h1>
          <p class="card-lead">
            {{ description }}
          </p>
        </div>
        <div class="btn-link">
          <a :class="`btn btn-${category}`" href="#">Learn More</a>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  place-content: center;
  align-items: center;
  min-height: 100vh;
}
.container {
  padding: 1.5rem;
}
img {
  height: auto;
}

a {
  all: unset;
}

.card {
  color: var(--very-light-gray);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 27rem;
  max-width: 19rem;
  padding: 3rem;
}

.card-description {
  padding: 1rem 0;
}

.card-title {
  font-family: var(--font-head);
  text-transform: uppercase;
  font-weight: 700;
  font-size: 2.5rem;
}

.card-lead {
  font-family: var(--font-body);
  padding: 1rem 0;
  /* opacity: 0.8; */
}

.card-sedans {
  background-color: var(--bright-orange);
  border-radius: 0.7rem 0.7rem 0 0;
}

.card-suvs {
  background-color: var(--dark-cyan);
}
.card-luxury {
  background-color: var(--very-dark-cyan);
  border-radius: 0 0 0.7rem 0.7rem;
}

.btn {
  font-family: var(--font-body);
  text-decoration: none;
  padding: 0.9rem 2rem;
  border-radius: 5rem;
  background-color: var(--very-light-gray);
  border: none;
  color: initial;
}

.btn-link {
  padding: 1rem 0;
}

.btn-sedans {
  color: var(--bright-orange);
}

.btn-suvs {
  color: var(--very-dark-cyan);
}

.btn-luxury {
  color: var(--very-dark-cyan);
}

.btn:hover {
  cursor: pointer;
  background: none;
  border: 1px solid var(--very-light-gray);
  color: var(--very-light-gray);
  transition: all 0.3s ease;
}

@media (width>=64rem) {
  .container {
    display: flex;
    flex-direction: row;
  }

  .card {
    min-height: 31.1rem;
  }

  .card-lead {
    font-size: 0.95rem;
  }

  .card-sedans {
    border-radius: 0.7rem 0 0 0.7rem;
  }

  .card-luxury {
    border-radius: 0 0.7rem 0.7rem 0;
  }
}
</style>
