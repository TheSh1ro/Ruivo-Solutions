<template>
  <main>
    <div id="content">
      <h1 class="title">Serviços de conserto</h1>
      <div class="container">
        <div
          class="item"
          :class="{ selected: selected == 'Computador' }"
          @click="selectItem('Computador')"
        >
          <p>Computador</p>
          <img src="/assets/computador.png" alt="" />
        </div>
        <div
          class="item"
          :class="{ selected: selected == 'Notebook' }"
          @click="selectItem('Notebook')"
        >
          <p>Notebook</p>
          <img src="/assets/notebook.png" alt="" />
        </div>
        <div
          class="item"
          :class="{ selected: selected == 'Celular' }"
          @click="selectItem('Celular')"
        >
          <p>Celular</p>
          <img src="/assets/celular.png" alt="" />
        </div>
        <div
          class="item"
          :class="{ selected: selected == 'Console' }"
          @click="selectItem('Console')"
        >
          <p>Console</p>
          <img src="/assets/console.png" alt="" />
        </div>
      </div>
      <button @click="sendService(selected)">Continuar</button>
    </div>
  </main>
</template>

<script>
export default {
  props: ['sendService'],
  data() {
    return {
      selected: 'Computador'
    }
  },
  created() {},
  computed: {},
  methods: {
    selectItem(name) {
      this.selected = name
    }
  }
}
</script>

<style scoped>
main {
  display: flex;

  transition:
    background-color 0.2s,
    color 0.2s,
    width 0.5s,
    height 0.5s;

  /* min-height: 100vh; */
  background-color: skyblue;
  color: white;
}

#content {
  padding: 60px;
  padding-top: 0px;

  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  text-align: center;
  flex-grow: 1;
  color: black;
  gap: 40px;
}

.title {
  border-bottom: 5px solid black;
  padding: 20px 100px;
  width: fit-content;
  margin-inline: auto;
}

.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, 350px);
  justify-content: center;
  gap: 30px;
  width: 100%;
}

.item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;

  font-size: 2rem;
  width: 350px;
  height: 350px;
  background-color: white;
  color: black;
  border: 3px solid black;
  border-radius: 30px;

  cursor: pointer;
  transition: background-color 0.5s border-color 1.5s;
}

.item img {
  height: 150px;
}

.item:hover {
  background-color: rgba(255, 255, 255, 0.3);
  box-shadow: 3px 3px 3px 3px black;
}

.selected {
  background-color: rgba(255, 255, 255, 0.3);
  box-shadow: 3px 3px 3px 3px black;
}

button {
  width: 50vw;
  font-size: 2rem;
  padding: 20px;
  border-radius: 15px;

  text-align: center;
  cursor: pointer;
  background-color: black;
  color: white;
}

button:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

@media (max-width: 800px) {
  .title {
    padding: 0px;
    margin: 0px auto;
    border-bottom: 1px solid black;
  }

  h1 {
    font-size: 1.5rem;
  }

  h2 {
    font-size: 1.2rem;
  }

  .container {
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .item {
    height: 40vw;
    width: 40vw;
    font-size: 1rem;
    gap: 10px;
  }

  .item img {
    height: 20vw;
  }

  button {
    font-size: 1.5rem;
  }
}
</style>
