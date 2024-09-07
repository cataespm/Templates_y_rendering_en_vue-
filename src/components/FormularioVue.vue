<script>
export default {
  name: 'H1DosPuntoCero',
  data() {
    return {
      colorFondo: 'purple',
      colorTexto: '',
      mostrar: '',
      border: '',
      tipoLetra: ['italic', 'normal', 'oblique'],
      tipoLetraSelected: '',
      opaco: '',
      tamañoLetraSelect: '',
      tamañoLetra: ['small', 'medium', 'large'],
      colores: ['pink', 'green', 'black', 'blue']
    }
  }
}
</script>
<template>
  <div class="col-4 bg-dark rounded-3 text-white" data-bs-theme="dark">
    <form class="">
      <div class="mb-3">
        <label for="titulo" class="col-sm-12 col-form-label">Color de fondo</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="colorFondo" v-model="colorFondo" />
        </div>
      </div>
      <div class="mb-3">
        <label for="titulo" class="col-sm-12 col-form-label">Color de texto</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="colorFondo" v-model="colorTexto" />
        </div>
      </div>
      <div class="row mb-3">
        <label for="mostrar" class="col-sm-12 col-form-label me-2">Mostrar Texto</label>
        <div class="col-sm-10">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="mostrar"
              value=""
              id="mostrar"
            />
            <label class="form-check-label" for="mostrar">mostrar</label>
          </div>
        </div>
      </div>
      <div class="flex">
        <label for="border" class="mb-3">borde</label>
        <input v-model="border" type="range" min="0" max="100" />
      </div>
      <div class="row mb-3">
        <label for="opinion" class="mb-3">contenido textual</label>
        <div class="col-sm-10">
          <textarea class="form-control" id="opinion" rows="3" v-model="opinion"></textarea>
        </div>
      </div>
      <div class="mb-3">
        <label for="tipoLetra" class="col-sm-2 col-form-label">Tipografia</label>
        <select
          v-model="tipoLetraSelected"
          class="form-select col-2"
          aria-label="Selector de tipoLetra"
        >
          <option v-for="(tipo, idx) in tipoLetra" :key="idx" :value="tipo">
            {{ tipo }}
          </option>
        </select>
      </div>
      <div class="form-check">
        <input
          class="form-check-input"
          type="checkbox"
          v-model="opaco"
          value="Morfología de un Componente"
          id="morfologia"
        />
        <label class="form-check-label" for="morfologia">Opaco</label>
      </div>
      <fieldset class="row mb-3">
        <legend class="col-form-label col-sm-12 me-2">Tamaño de letra</legend>
        <div class="col-sm-10">
          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="chico"
              value="small"
              v-model="tamañoLetraSelect"
            />
            <label class="form-check-label" for="chico">pequeño</label>
          </div>
          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="mediano"
              value="medium"
              v-model="tamañoLetraSelect"
            />
            <label class="form-check-label" for="mediano"> mediano </label>
          </div>
          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="grande"
              value="large"
              v-model="tamañoLetraSelect"
            />
            <label class="form-check-label" for="grande"> grande </label>
          </div>
        </div>
      </fieldset>
    </form>
  </div>
  <div
    id="resultado"
    :class="{ 'opacity-25': opaco == true }"
    class="col-8 cuadrado d-flex flex-wrap justify-content-center text-break"
    v-bind:style="{
      'border-radius': border + 'px',
      'background-color': colorFondo,
      'vertical-align': center
    }"
  >
    <p
      v-if="mostrar"
      v-bind:style="{ color: colorTexto, 'font-style': tipoLetraSelected }"
      v-bind:class="tamañoLetraSelect"
    >
      {{ opinion }}
    </p>
  </div>
</template>

<style scoped>
.cuadrado {
  width: 400px;
  height: 400px;
  margin-left: 2rem;
}
.small {
  font-size: 15px;
}
.medium {
  font-size: 30px;
}
.large {
  font-size: 50px;
}
</style>
