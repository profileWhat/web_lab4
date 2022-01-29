<template>
  <div class="content">
    <div class="div-field">
    <Page/>
    </div>
        <div class="div-field">
          <h2 class="UI-header">Authentication</h2>
          <form>
            <div>
              <div >
                <label>
                  <input class="text-input" type="text" name="username" placeholder="Логин" v-model.trim = "username">
                </label>
              </div>
            </div>
            <div>
              <div >
                <label>
                  <input class="text-input" type="password" name="password" placeholder="Пароль" v-model.trim = "password">
                </label>
              </div>
            </div>
            <div>
              <button class="set-button" style="width: 168px" @click="login">
                Ввойти
              </button>
              <div></div>
              <button class="set-button" style="width: 168px" @click="register">
                Регистрация
              </button>
            </div>
          </form>
        </div>
    <div class="div-field">
      <Clock/>
    </div>
  </div>
</template>

<script>

import Page from "@/components/Page";
import Clock from "@/components/Clock";
export default {
  name: "Auth",

  data() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    login(event) {
      event.preventDefault();
      this.axios.post("http://localhost:8082/auth/login", {
        username: this.username,
        password: this.password
      }).then(response => {
        localStorage.setItem("jwt", response.data);
        this.$router.push('main');
      }).catch(() => {
        alert("Неправильный пароль или логин!");
      })
    },
    register(event) {
      event.preventDefault();
      this.axios.post("http://localhost:8082/auth/register", {
        username: this.username,
        password: this.password
      }).then(() => {
        alert("Пользователь успешно зарегистрирован!");
      }).catch(()=> {
        alert("Пользователь с таким логином уже есть!");
      })
    }
  },
  components: {
    Page,
    Clock,
  },
}
</script>




