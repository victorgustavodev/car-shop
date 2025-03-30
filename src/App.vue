<template>
  <div class="flex h-screen" :style="{ background: `radial-gradient(circle, #fff 1%, ${selectedCar.colorMain} 70%)` }">
    
    <Navbar :backgroundColor="selectedCar.colorMain" />

    <div class="flex flex-col w-full justify-center items-center">

      <div class="h-full w-full gap-10 flex justify-start items-center">

        <section class="w-[30%] flex justify-center pt-10 h-full rounded-lg">
          <div class="flex flex-col w-4/5 gap-6 text-start text-white">
            <h1 class="text-3xl font-extrabold md:text-xl">Select a Car</h1>
            <hr class="w-1/3 h-[2px] bg-white rounded-lg mb-4" />
            <form class="w-full">
              <div class="flex flex-col gap-4">
          <label for="car-select" class="text-lg font-semibold md:text-sm">Choose your car:</label>
          <select id="car-select" v-model="selectedCarId"
            class="w-full h-[50px] border-2 border-gray-600 text-white rounded-md p-2 text-lg font-bold md:h-[40px] md:text-sm focus:outline-none focus:ring-2 focus:ring-blue-500" :style="{ background: selectedCar.colorMain }">
            <option v-for="car in cars" :key="car.id" :value="car.id">{{ car.brand }}</option>
          </select>
              </div>
            </form>
            
            <div class="flex flex-col items-start gap-4 text-lg font-medium md:text-sm">
              <p class="text-2xl font-bold md:text-lg">{{ selectedCar.name }}</p>
              <div class="flex gap-3 items-center text-base md:text-sm">
          <p>{{ selectedCar.year || 'Year not available' }}</p>
          <span>|</span>
          <p>{{ selectedCar.manufacturer || 'Manufacturer not available' }}</p>
              </div>
              <div class="flex flex-col gap-4">
          <p class="text-3xl font-extrabold uppercase md:text-xl">{{ selectedCar.price }}</p>
          <button
            @click= 'buyNow()' class="h-[40px] px-10 w-fit bg-blue-600 text-white cursor-pointer font-bold rounded-lg uppercase transition-all hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500">
            Buy Now
          </button>
              </div>
            </div>
          </div>
        </section>

        <MainImage :selectedCar="selectedCar" />

      </div>
    </div>

  </div>
</template>

<script>

import MainImage from "./components/MainImage.vue";
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
    MainImage
  },

  methods: {
    buyNow() {
      alert(`You selected: ${this.selectedCar.name} \nIts price is: ${this.selectedCar.price}`);
    },
  },
  name: 'App',
  data() {
    return {
      isIdSelected: 1,
      myData: null,
      cars: [
      { id: 1, name: 'Mini John Cooper Works', brand: "Mini", year: 2022, manufacturer: "BMW", price: '$35,000', image: require('@/assets/Car-1.png'), colorMain: "gray" },
      { id: 2, name: 'Opel Rekord', brand: "Opel", year: 1985, manufacturer: "Opel", price: '$12,000', image: require('@/assets/Car-2.png'), colorMain: "#59B6E6" },
      { id: 3, name: 'Buick Roadmaster', brand: "Buick", year: 1957, manufacturer: "General Motors", price: '$45,000', image: require('@/assets/Car-3.png'), colorMain: "#B40500" },
      { id: 4, name: 'Cadillac Eldorado', brand: "Cadillac", year: 1959, manufacturer: "General Motors", price: '$75,000', image: require('@/assets/Car-4.png'), colorMain: "#FF9597" },
      { id: 5, name: 'Ford Mustang Boss 429', brand: "Ford", year: 1969, manufacturer: "Ford", price: '$200,000', image: require('@/assets/Car-5.png'), colorMain: "#9a7936" },
      { id: 6, name: 'Chevrolet Special Deluxe', brand: "Chevrolet", year: 1941, manufacturer: "General Motors", price: '$30,000', image: require('@/assets/Car-6.png'), colorMain: "#16151a" },
      ],
      selectedCarId: null
    };
  },
  created() {
    this.selectedCarId = this.isIdSelected;
  },
  computed: {
    selectedCar() {
      return this.cars.find(car => car.id === this.selectedCarId) || {};
    },
  },
};
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}

body {
  color: white;
}



ul {
  writing-mode: vertical-lr;
  transform: rotate(180deg);
}

.pt-10 {
  padding-top: 2.5rem;
}

.px-10 {
  padding-left: 2.5rem;
  padding-right: 2.5rem;
}
</style>