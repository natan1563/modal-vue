<template>
  <div id="app">
    <button @click="modalActive = true">Abrir modal</button>
    <transition name="modal">
      <div class="modal" v-if="modalActive">
        
        <div class="modal-content">
          <p id="close" @click="modalActive = false">X</p>

          <label for="userName" class="labelUser">Nome de usuario</label>
          <div>
            <input type="text" name="userName" id="userName">
          </div>
          
          <label for="password" class="labelPassword">Senha</label>
          <div>
            <input type="password" name="password" id="password">
          </div>
          
          <button class="btnEntrar">Entrar</button>

          <label for="remember" class="labelRemember">
            <input type="checkbox" name="remember" id="remember">
            <span>Lembre-se de mim</span>
          </label>
        </div>

      </div>
    </transition>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      modalActive: false
    }
  },

}
</script>

<style scoped>
  .modal {
    display: block;
    position: fixed;
    z-index: 1;
    width: 100%;
    height: 100vh;
    top: 0;
    left: 0;
    background: rgba(0, 0, 0, .4);
  }

  .modal-content {
    position: relative;
    margin: 200px auto;
    max-width: 300px;
    max-height: 300px;
    text-align: center;
    background: #ffff;
    border-radius: 10px;
  }
  
  #close {
    position: absolute;
    top: 0;
    right: 0;
    margin: 0px;
    padding: 1px 5px;
    background: #7a7878;
    border-radius: 6px;
    color: #ffff;
    cursor: pointer;
  }
  
  .labelPassword,
  .labelUser {
    display: block;
    padding-top: 15px;
    margin-bottom: 5px;
  }

  .labelRemember {
    display: block;
    padding-bottom: 15px;
  }
  
  .btnEntrar {
    margin: 15px 0;
    padding: 8px 10px;
    background: rgb(8, 206, 241);
    border: 1px solid rgb(127, 223, 240);
    border-radius: 7px;
    color: rgb(19, 16, 16);
    font-weight: bold;
  }

  .modal-enter-active,
  .modal-leave-active {
    transition: opacity 2s;
  }

  .modal-enter,
  .modal-leave-to {
    opacity: 0;
  }
</style>
