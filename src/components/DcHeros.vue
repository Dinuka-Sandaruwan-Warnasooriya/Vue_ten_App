<template>
  <div class="m-auto">
    <h1 class="text-2xl text-center py-5">DC Heros {{ herosCount }}</h1>
    <ul>
      <li
        class="flex justify-between"
        v-for="(hero, index) in dcHeros"
        :key="index"
      >
        {{ hero.name }} <button @click="removeHero(index)">X</button>
      </li>
    </ul>
    <form class="mt-10" @submit.prevent="addHero()">
      <input
        class="border rounded"
        v-model="newHero"
        placeholder="Type the hero name"
      />
      <button
        class="border rounded bg-gradient-to-t from-transparent-to-r from-red-600 to-pink-500 text-white text-sm"
        type="submit"
      >
        Add Hero
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dcHeros: [{ name: "Super Man" }, { name: "Bat Man" }, { name: "Flash" }],

      newHero: "",
    };
  },

  computed: {
    herosCount() {
      return this.dcHeros.length;
    },
  },

  methods: {
    addHero() {
      this.dcHeros.push({ name: this.newHero });
      alert("Hero Added");
    },
    removeHero(index) {
      this.dcHeros = this.dcHeros.
      filter((hero, i) => i !== index);
    },
  },
};
</script>

<style lang=""></style>
