<template>
  <div class="flex h-screen" :style="{ background: selectedCar.colorMain || '#b40600' }">
    <nav class="flex flex-col items-center w-[107px] h-screen shadow-xl shadow-black md:w-[80px]" :style="{ background: selectedCar.colorMain || '#b40600' }">
      <div class="bg-white w-full min-h-[170px] flex justify-center items-center md:min-h-[100px]">
        <img src="./assets/logo.png" alt="Logo" class="w-[80px] md:w-[60px]">
      </div>
      <div class="h-full flex justify-center items-center w-full">
        <ul class="uppercase text-center flex justify-between items-center h-4/5 text-[16px] font-bold md:text-[12px]">
          <li>cadilac</li>
          <li>lincoln</li>
          <li>chevrolet</li>
          <li>citroen</li>
          <li>mercedes</li>
        </ul>
      </div>
    </nav>

    <div class="flex flex-col w-full justify-center items-center p-5">
      <div class="flex flex-col w-[800px] h-[800px] gap-10 items-center justify-center mt-10 text-center">
        <div class="flex flex-col gap-3">
          <h1 class="text-4xl font-bold md:text-2xl">Selecione um carro</h1>
          <p class="text-lg font-bold md:text-sm">Selecione um carro para ver mais detalhes</p>
          
          <form action="" class="w-full max-w-[400px]">
            <div class="flex flex-col gap-5 items-center justify-center mt-10">
              <select id="car-select" v-model="selectedCarId" class="w-full h-[50px] border-2 rounded-md p-2 text-black text-lg font-bold md:h-[40px] md:text-sm">
                <option class="text-black" v-for="car in cars" :key="car.id" :value="car.id">{{ car.brand }}</option>
              </select>
            </div>
          </form>
        </div>

        <div class="h-full w-full flex justify-center items-center pt-10">
          <section class="flex flex-col gap-20 items-center justify-center text-center">
            <img :src="selectedCar.image" :alt="selectedCar.name" class="w-[800px] h-auto max-h-[450px]" />
            <div class="flex flex-col items-center justify-center gap-5 text-4xl font-bold md:text-lg">
              <p>{{ selectedCar.brand }}</p>
              <div class="grid grid-cols-1 gap-5">
                <p class="uppercase text-5xl">{{ selectedCar.price }}</p>
                <button class="border-2 border-white p-4 w-full rounded-lg uppercase hover:bg-red-500 cursor-pointer transition-all">buy</button>
              </div>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isIdSelected: 1,
      myData: null,
      cars: [
        { id: 1, name: 'Car 1', brand: "Cadillac Imperial", price: '$20,000', image: require('@/assets/Car-1.png'), colorMain: "#212126" },
        { id: 2, name: 'Car 2', brand: "OPEL Rekord", price: '$25,000', image: require('@/assets/Car-2.png'), colorMain: "#59B6E6" },
        { id: 3, name: 'Car 3', brand: "Buick Road Master", price: '$30,000', image: require('@/assets/Car-3.png'), colorMain: "#B40500" },
        { id: 4, name: 'Car 4', brand: "Voiture Cadillac Rose", price: '$50,000', image: require('@/assets/Car-4.png'), colorMain: "#FF9597" },
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

body
{
  color: white;
}

ul {
  writing-mode: vertical-lr;
  transform: rotate(180deg);
}
</style>