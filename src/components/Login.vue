<template>
  <div id="login">
    <img src="../assets/logo.png" class="img-inicial" />
    <el-form label-width="100px" class="form-login" :model="formLabelAlign">
      <el-input
        placeholder="Correo electrónico"
        v-model="formLabelAlign.user"
      ></el-input>
      <el-input
        type="password"
        placeholder="Contraseña"
        v-model="formLabelAlign.password"
        autocomplete="off"
      ></el-input>
      <el-button type="primary" class="ingresar-login" @click="login"
        >Ingresar</el-button
      >
    </el-form>
  </div>
</template>
<script>
import { getAuth, signInWithEmailAndPassword } from "firebase/auth";
//
export default {
  data() {
    return {
      formLabelAlign: {
        user: "",
        password: "",
      },
    };
  },
  methods: {
    login() {
      const auth = getAuth();
      console.log(auth);
      const {
        formLabelAlign: { user: email, password },
      } = this;
      signInWithEmailAndPassword(auth, email, password)
        .then((userCredential) => {
          // Signed in
          const user = userCredential.user;
          console.log(user);
          // ...
          this.$router.push("/home");
        })
        .catch((error) => {
          //const errorCode = error.code;
          const errorMessage = error.message;
          alert(errorMessage);
        });
    },
  },
};
</script>
<style scoped>
</style>