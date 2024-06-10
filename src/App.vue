<template>
  <div class="row g-4 mt-5">
    <div class="col-5 p-4 border border-secondary rounded formulario">
      <form action="">
        <div class="mb-3 mx-3">
          <label for="colorFondo" class="form-label text-light"
            >Color de Fondo</label
          >
          <input
            type="text"
            class="form-control form-control-sm"
            id="colorFondo"
            name="colorFondo"
            v-model="figura.colorDeFondo"
          />
        </div>
        <div class="mb-3 mx-3">
          <label for="colorTexto" class="form-label text-light"
            >Color de Texto</label
          >
          <input
            type="text"
            class="form-control form-control-sm"
            id="colorTexto"
            name="colorTexto"
            v-model="figura.color"
          />
        </div>

        <div class="mb-3 mx-3">
          <div
            class="form-check form-check-reverse d-flex justify-content-start"
          >
            <label class="form-check-label text-light me-2" for="mostrarTexto"
              >Mostrar Texto</label
            >
            <input
              class="form-check-input"
              type="checkbox"
              id="mostrarTexto"
              value=""
              v-model="figura.verTexto"
            />
          </div>
        </div>

        <div class="mb-3 mx-3">
          <label for="customRange3" class="form-label text-light">Borde</label>
          <input
            type="range"
            class="form-range"
            min="0"
            max="200"
            id="customRange3"
            v-model="figura.borderRadius"
          />
        </div>

        <div class="mb-3 mx-3">
          <label for="contenidoTextual" class="form-label text-light"
            >Contenido Textual
          </label>
          <textarea
            class="form-control"
            id="contenidoTextual"
            rows="2"
            v-model="figura.texto"
          ></textarea>
        </div>

        <div class="mb-3 mx-3">
          <label for="tipografia" class="form-label text-light"
            >Tipografia</label
          >
          <select
            id="tipografia"
            class="form-select"
            v-model="figura.fontFamily"
          >
            <option value="Helvetica" selected>Helvetica</option>
            <option value="Roboto">Roboto</option>
            <option value="sans-serif">Sans-serif</option>
          </select>
        </div>

        <div class="mb-3 mx-3">
          <div
            class="form-check form-check-reverse d-flex justify-content-start"
          >
            <label class="form-check-label text-light me-2" for="opaco"
              >Opaco</label
            >
            <input
              class="form-check-input"
              type="checkbox"
              id="opaco"
              value=""
              v-model="figura.opacidad"
            />
          </div>
        </div>

        <div class="row mb-3 mx-2">
          <div class="col-sm-12">
            <span class="text-light">Tamaño de letra</span>
          </div>
          <div class="col-sm-12">
            <div class="form-check form-check-inline">
              <input
                class="form-check-input"
                type="radio"
                name="inlineRadioOptions"
                id="inlineRadio1"
                value="Smaller"
                v-model="figura.fontSize"
              />
              <label class="form-check-label text-light" for="inlineRadio1"
                >Pequeño</label
              >
            </div>
            <div class="form-check form-check-inline">
              <input
                class="form-check-input"
                type="radio"
                name="inlineRadioOptions"
                id="inlineRadio2"
                value="Medium"
                v-model="figura.fontSize"
              />
              <label class="form-check-label text-light" for="inlineRadio2"
                >Mediano</label
              >
            </div>
            <div class="form-check form-check-inline">
              <input
                class="form-check-input"
                type="radio"
                name="inlineRadioOptions"
                id="inlineRadio3"
                value="Larger"
                v-model="figura.fontSize"
              />
              <label class="form-check-label text-light" for="inlineRadio4"
                >Grande</label
              >
            </div>
          </div>
        </div>
      </form>
    </div>
    <div class="col-7 p-4 d-flex justify-content-center align-items-center">
      <div
        class="figura d-flex justify-content-center align-items-center"
        v-show="figura.opacidad"
        :style="{
          backgroundColor: figura.colorDeFondo,
          borderRadius: figura.borderRadius + 'px',
          color: figura.color,
          fontSize: figura.fontSize,
          fontFamily: figura.fontFamily,
        }"
      >
        <div
          class="textContainer d-flex justify-content-center align-items-center"
          v-if="figura.verTexto"
        >
          <p class="text-center">{{ figura.texto }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      figura: {
        opacidad: true,
        verTexto: true,
        colorDeFondo: "green",
        borderRadius: "0px",
        color: "white",
        fontFamily: "Helvetica",
        fontSize: "medium",
        texto: "",
      },
    };
  },
};
</script>

<style>
.formulario {
  background-color: #003c00;
}

.figura {
  margin: 10px;
  border: solid 1px;
  height: 50%;
  width: 50%;
}
</style>
