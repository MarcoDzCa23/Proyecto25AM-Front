<template>
  <div class="container">
    <h1 class="title">Inicio de sesion</h1>
    <form action class="form" @submit.prevent="login">
      <label class="form-label" for="#email">Email:</label>
      <input class="form-input" type="email" id="email" required placeholder="Email">
      <label class="form-label" for="#password">Password:</label>
      <input class="form-input" type="password" id="password" placeholder="Password">
      <input class="form-submit" type="submit" value="Login">
    </form>
  </div>
</template>

<script>
export default {
  data: () => ({
    email: "",
    password: ""
  }),
  methods: {
    login() {
      console.log(this.email);
      console.log(this.password);
      this.$router.push("/Dashboard")
    }
  }
};
</script>

<style lang="scss" scoped>
.container {
  // padding: 2rem;
  // display: flex;
  // justify-content: center; /* Centra horizontalmente el contenido */
  // align-items: center; /* Centra verticalmente el contenido */
    // display: flex;
    // place-items: flex-start;
    // flex-wrap: wrap;
  display: flex;
  flex-direction: column; /* Asegura que los elementos se apilen verticalmente */
  justify-content: center; /* Centra verticalmente el contenido */
  align-items: center; /* Centra horizontalmente el contenido */
  height: 100vh; /* Ajusta la altura del contenedor al 100% de la ventana */
  margin: 0 auto;
  padding: 0 ;
  
}
.title {
  text-align: center;

}
.form {
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 20%;
  min-width: 350px;
  max-width: 100%;
  background: rgba(19, 35, 47, 0.9);
  border-radius: 5px;
  padding: 40px;
  box-shadow: 0 4px 10px 4px rgba(0, 0, 0, 0.3);
  
}
.form-label {
  margin-top: 2rem;
  color: white;
  margin-bottom: 0.5rem;
  &:first-of-type {
    margin-top: 0rem;
  }
}
.form-input {
  padding: 10px 15px;
  background: none;
  background-image: none;
  border: 1px solid white;
  color: white;
  &:focus {
    outline: 0;
    border-color: #1ab188;
  }
}
.form-submit {
  background: #1ab188;
  border: none;
  color: white;
  margin-top: 3rem;
  padding: 1rem 0;
  cursor: pointer;
  transition: background 0.2s;
  &:hover {
    background: #0b9185;
  }
}
</style>