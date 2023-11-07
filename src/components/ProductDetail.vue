<template>
    <div v-if="bike" class="motorcycle-details">
      <h1>{{ bike.brand }} {{ bike.model }}</h1>
      <img :src="bike.image" alt="Moto" class="motorcycle-image">
      <div class="motorcycle-info">
        <p><strong>Brand:</strong> {{ bike.brand }}</p>
        <p><strong>Model:</strong> {{ bike.model }}</p>
        <p><strong>Displacement:</strong> {{ bike.displacement }}</p>
      </div>
    </div>
    <div v-else class="motorcycle-details">
        <H1>No bike for this ID</H1>
    </div>
  </template>
<script lang="ts">
import bikes from "@/assets/bikes.json";
export default {
    data() {
        return {
            bikes: bikes
        }
    },
    computed: {
        bike() {
            const id = this.$route.params.id;
            const numId = parseInt(id);
            if (!isNaN(numId)) {
                return this.bikes.find(moto => moto.id === numId);
            } else {
                return false
            }
        }
    }
}
</script>
  
<style>
  .motorcycle-details {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px;
  }

  .motorcycle-image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    margin: 20px 0;
  }

  .motorcycle-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 20px;
  }

  .motorcycle-info p {
    margin: 5px;
  }

  .motorcycle-info strong {
    font-weight: bold;
  }
</style>