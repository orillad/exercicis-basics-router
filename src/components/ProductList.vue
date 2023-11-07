<template>
    <div class="motorcycle-list">
        <h1>List of motorbikes</h1>
        <ul>
            <li v-for="moto in bikes" :key="moto.id" class="motorcycle-item">
                <h1><router-link :to="'/products/' + moto.id">{{ moto.brand }} {{ moto.model}}</router-link></h1>
                <div class="motorcycle-details">
                    <img :src="moto.image" alt="Moto" class="motorcycle-image">
                    <div class="motorcycle-info">
                        <p><strong>Brand:</strong> {{ moto.brand }}</p>
                        <p><strong>Model:</strong> {{ moto.model }}</p>
                        <p><strong>Displacement:</strong> {{ moto.displacement }}</p>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>
  
<script lang="ts">
import bikes from "@/assets/bikes.json";
export default {
    data() {
        return {
            bikes: bikes
        }
    }
}
</script>
  

<style scoped>
.motorcycle-list {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;

}

.motorcycle-item {

    border: 1px solid #ccc;
    margin-bottom: 20px;
    padding: 10px;
    border-radius: 5px;
    background-color: #f9f9f9;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.motorcycle-details {
    display: flex;
    align-items: center;
}

.motorcycle-image {
    width: 300px;
    margin-right: 20px;
    border-radius: 5px;
}

.motorcycle-info {
    flex: 1;
}

h1 {
    text-align: center;
}
</style>