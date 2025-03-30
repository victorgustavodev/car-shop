<template>
  <nav class="flex flex-col items-center w-full md:w-[107px] h-fit md:h-screen shadow-xl shadow-black md:w-[80px]"
    :style="{ background: backgroundColor }">
    <div class="bg-white w-full min-h-[170px] flex justify-center items-center md:min-h-[100px]">
      <img src="./assets/logo.png" alt="Logo" class="w-[80px] md:w-[60px]">
    </div>
    <div class="md:h-full w-full flex justify-center items-center">
      <ul class="uppercase md:tracking-widest text-center flex justify-between items-center h-4/5 text-[16px] font-bold md:text-[12px]">
        <li>cadilac</li>
        <li>lincoln</li>
        <li>chevrolet</li>
        <li>citroen</li>
        <li>mercedes</li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    backgroundColor: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
/* Adicione estilos específicos para o componente aqui, se necessário */
</style>