<script>

export default {
  name: 'Login',
  data() {
    return {
      form: {
        name: "",
        email: "",
        date: "",
        tel: "",
        radio: "",
        usuario: "",
        senha: "",
        msg: ""
      },
    };
  },
  methods: {
    checkForm: function (e) {
      if ((this.name && this.email && this.date && this.tel && this.radio) || (this.text && this.password)) {
        return true;
      }

      this.errors = [];
      this.errors.push('Todos os campos são obrigatórios.');
      e.preventDefault();
    }
  }
}

</script>

<template>
  <NuxtLayout>
    <div class="font-sans font-bold text-green-900 bg-emerald-50 p-4">
      <h1 class="text-4xl m-5">Cadastro e Login</h1>
    </div>
    <AppHeader />
    <v-content>
      <div class="flex row">
        <div id="forms" class="w-1/2 h-1/2">
          <form id="app" @submit="checkForm" method="post"
            class="bg-emerald-100 text-green-900 border-lime-900 leading-8 p-6 flex">
            <h2 class="font-mono text-lg">Cadastrar</h2>
            <div>
              <label for="name"><b><u>Nome</u>:</b></label>
              <input v-model="name" type="text" name="name" placeholder="Digite seu nome" required>
            </div>
            <div>
              <label for="email"><b><u>Email</u>:</b></label>
              <input v-model="email" type="email" name="email" placeholder="Digite seu email" required>
            </div>
            <div>
              <label for="date"><b><u>Data de nascimento</u>:</b></label>
              <input v-model="date" type="date" name="nascimento" required>
            </div>
            <div>
              <label for="telefone"><b><u>Telefone</u>:</b></label>
              <input v-model="tel" type="number" name="telefone" id="telefone"
                placeholder="Digite seu Telefone" required>
            </div>
            <div>
              <label for="radio"><b><u>Sexo</u>:</b></label>
              <div>
                <input v-model="radio" type="radio" name="sexo" id="fem" required>
                <label for="fem">Feminino</label><br>
                <input v-model="radio" type="radio" name="sexo" id="masc" required>
                <label for="masc">Masculino</label><br>
              </div>
            </div>
            <button type="submit"
              class="flex text-lg border-2 rounded-lg border-green-900 p-2.5 m-2.5"><b>Enviar</b></button>
          </form>
        </div>
        <div id="forms">
          <form id="app" @submit="checkForm" method="post"
            class="bg-emerald-100 text-green-900 border-lime-900 leading-8 p-6 flex">

            <h2 class="font-mono text-lg">Entrar</h2>
            <div>
              <label for="text"><b><u>Usuário</u>:</b></label>
              <input v-model="text" type="text" name="text" placeholder="Digite seu usuário" required>
            </div>
            <div>
              <label for="email"><b><u>Senha</u>:</b></label>
              <input v-model="password" type="password" name="senha" placeholder="Digite sua senha" required>
            </div>
            <button type="submit"
              class="flex text-lg border-2 rounded-lg border-green-900 p-2.5 m-2.5"><b>Enviar</b></button>
          </form>
        </div>
      </div>
    </v-content>
    <v-footer>
      <div class="bg-emerald-50 p-12 border-green-900 text-green-900"></div>
    </v-footer>

  </NuxtLayout>
</template>

<style scoped>
form {
  flex-direction: column;
  justify-content: center;
}

input {
  margin: 10px;
  border: 1px solid #14532d;
}

label {
  margin: 10px;
}



h2,
h1 {
  text-align: center;
  padding: 5px;
}

button {
  justify-content: center;
}

#forms {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 50px;
}
</style>