<template>
    <section class="flex flex-col w-[70%] h-full gap-10 items-center justify-center mt-10 text-center">
        <div class="h-full w-full flex justify-center items-center pt-10">
          <section class="flex flex-col gap-20 items-center justify-center text-center">
            <img :src="selectedCar.image" :alt="selectedCar.name" class="w-[90%] max-w-[90%]" />
          </section>
        </div>
      </section>
</template>

<script>

export default {
  name: 'MainImage',
  props: {
    selectedCar: {
      type: Object,
      required: true,
    },
  },
};

</script>