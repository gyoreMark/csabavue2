<template>
  <div class="hello">
    <div class="datum">
      <form>
        <div class="mb-3">
          <label for="datum1" class="form-label">Dátum 1:</label>
          <input
            type="date"
            class="form-control"
            id="datum1"
            name="datum1"
            v-model="datum1"
          />
        </div>

        <div class="mb-3">
          <label for="datum2" class="form-label">Dátum 2:</label>
          <input
            type="date"
            class="form-control"
            id="datum2"
            name="datum2"
            v-model="datum2"
          />
        </div>

        <button
          type="submit"
          class="btn btn-primary"
          id="checkBtn"
          @click="checkDate"
        >
          Megfejtés
        </button>

        <p id="alertMessageRed">A két dátum nem azonos!</p>
        <p id="alertMessageGreen">A két dátum azonos!</p>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      datum1: undefined,
      datum2: undefined,
    };
  },

  methods: {
    checkDate() {
      if ((this.datum1 = !this.datum2)) {
        document.getElementById("alertMessageRed").style.display = "block";
      } else {
        document.getElementById("alertMessageGreen").style.display = "block";
      }
    },
    addDate() {},
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(216, 231, 128);
  top: 0;
  left: 0;
}

#alertMessageRed {
  display: none;
  color: red;
}

#alertMessageGreen {
  display: none;
  color: green;
}

.btn {
  margin-top: 20px;
  width: 150px;
}
</style>
