<template>
  <div>
    <b-form-textarea v-model="mensaje" placeholder="Comentar"></b-form-textarea>
    <b-form-input
      class="mt-2"
      placeholder="Autor"
      v-model="autor"
    ></b-form-input>
    <b-button class="mt-2" variant="primary" @click="enviarComentario()">
      Comentar
    </b-button>
  </div>
</template>

<script>
export default {
  props: {
    id: Number,
  },
  data() {
    return {
      mensaje: "",
      mensajeId: "",

      autor: "",
    };
  },
  created() {
    this.mensajeId = this.id;
    console.log(this.id);
  },
  methods: {
    enviarComentario() {
      this.$emit("comentario", this.mensaje, this.mensajeId, this.autor);
      this.mensaje = "";
      this.autor = " ";
    },
  },
};
</script>

<style></style>
