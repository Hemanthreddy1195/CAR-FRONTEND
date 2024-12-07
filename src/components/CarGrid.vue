<template>
    <div class="car-grid">
      <div class="car">
        <img src="../assets/HONDA_accord.jpg" @click="fetchCarData('Accord')" />
      </div>
      <div class="car">
        <img src="../assets/HONDA_crv_hybrid.png" @click="fetchCarData('HondaCRV')" />
      </div>
      <div class="car">
        <img src="../assets/HY_hybrid.png" @click="fetchCarData('HYHybrid')" />
      </div>
      <div class="car">
        <img src="../assets/HY_tucson.jpg" @click="fetchCarData('HYTucson')" />
      </div>
      <div class="car">
        <img src="../assets/TOYOTA_Aygo.jpg" @click="fetchCarData('ToyotaAygo')" />
      </div>
      <div class="car">
        <img src="../assets/VK_jetta.avif" @click="fetchCarData('VKJetta')" />
      </div>
      <div class="car">
        <img src="../assets/VK_taigo.jpg" @click="fetchCarData('VKTaigo')" />
      </div>
      <div class="car">
        <img src="../assets/FORD_focus.avif" @click="fetchCarData('FordFocus')" />
      </div>
    </div>
  
    <div v-if="carData" class="car-data" ref="carDataDiv">
      <h2 >{{ carData.name }}</h2>
      <p><strong>Model Year:</strong> {{ carData.modelYear }}</p>
      <p><strong>Mileage:</strong> {{ carData.mileage }} miles</p>
      <p><strong>Previous Owner:</strong> {{ carData.previousOwnerName }}</p>
      <p><strong>Rent per Month:</strong> ${{ carData.rentPerMonth }}</p>
      <p><strong>Price to Buy:</strong> ${{ carData.priceToBuy }}</p>
      <p><strong>Estimated Insurance:</strong> ${{ carData.estimatedInsurance }}</p>
      <p><strong>Remarks:</strong> {{ carData.anybodyRemarks }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CarGrid',
    data() {
      return {
        carData: null, // Property to store the fetched car data
      };
    },
    methods: {
      // Method to fetch car data from the API
      async fetchCarData(carName) {
        try {
          // Send a GET request to your backend API to get the car data by name
          const response = await fetch(`https://car-backend-oaup.onrender.com/api/cars/${carName}`);
          console.log(response.body);
          if (!response.ok) {
            throw new Error('Car not found');
          }
  
          this.carData = await response.json(); // Store the fetched data in carData
  
          // Scroll to the car data section once data is fetched
          this.scrollToCarData();
          
        } catch (error) {
          console.error('Error fetching car data:', error);
          // Handle errors appropriately, e.g., show an error message to the user
        }
      },
  
      // Method to scroll to the car data section
      scrollToCarData() {
        const carDataDiv = this.$refs.carDataDiv; // Get the reference to the car data div
        if (carDataDiv) {
          carDataDiv.scrollIntoView({ behavior: 'smooth' }); // Smooth scroll to the section
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .car-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    background-color: rgb(10, 6, 20);
    gap: 5%;
    padding: 10%;
  }
  
  .car {
    cursor: pointer; /* Make the image clickable */
  }
  
  img {
    width: 80%;
    height: 100%;
  }
  
  .car-data {
    margin-top: 20px;
    color: white;
    font-family: Arial, sans-serif;
  }
  
  .car-data h2 {
    font-weight: bolder;
    color: red;
    font-size: 3rem;
  }
  
  .car-data p {
    font-size: 2rem;
    color: black;
  }
  </style>
  