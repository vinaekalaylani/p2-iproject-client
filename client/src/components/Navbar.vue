<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-light shadow sticky-top">
            <div class="container-fluid">
                <label class="navbar-brand" aria-current="page">👩‍🚀 Todoin</label>
                <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent"
                aria-expanded="false"
                aria-label="Toggle navigation"
                >
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <router-link to="/home" class="nav-link active" aria-current="page">Todos</router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/chat" class="nav-link active" aria-current="page">Chat</router-link>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link active" aria-current="page" href="#" v-on:click.prevent="logout">Logout</a>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
import { success } from '../apis/alert'
export default {
  name: 'Navbar',
  methods: {
    logout () {
      localStorage.clear()
      success('See You Broo 👋')
      this.$store.commit('SET_IS_LOGIN', false)
      this.$router.push('/')
    }
  },
  computed: {
    isLogin () {
      return this.$store.state.isLogin
    }
  }
}
</script>

<style>
.navbar{
  position: fixed;
  top: 10;
  width: 100%;
  height: 60px;
}
</style>
