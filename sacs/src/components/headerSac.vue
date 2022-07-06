<template>
  <header>
    <form action="">
      <label for="">Usuário</label>
      <input
        type="text"
        name="user-input"
        disabled
        value="LUCAS DE FREITAS OLIVEIRA"
      />
    </form>
  </header>
</template>

<script>
export default {
  name: "headerSac",
  props: {
    msg: String,
  },
};
</script>
<style>
input {
  background: grey;
}
</style>
