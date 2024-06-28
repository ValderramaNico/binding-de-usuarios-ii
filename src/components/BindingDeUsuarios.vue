<template>
  <div class="container">
    <form class="leftForm">
      <div class="leftForm-sections">
        <label class="form-title">Título: </label>
        <input class="form-input" type="text" v-model="user.title">
      </div>
      <hr>
      <div class="leftForm-sections">
        <label class="form-title">Emoji: </label>
        <select class="form-emoji" name="emoji-selection" id="emoji-choice" v-model="user.emoji">
          <option value="🧑‍💻">🧑‍💻</option>
          <option value="🤖">🤖</option>
          <option value="👾">👾</option>
        </select>
      </div>
      <hr>
      <div class="leftForm-sections">
        <label class="form-title">Apreciación: </label>
        <div class="form-radio">
          <div>
            <input class="radio-selection" type="radio" name="radio-selected" id="regular" value="Regular" v-model="user.radio">
            <label>Regular</label>
          </div>
          <div>
            <input class="radio-selection" type="radio" name="radio-selected" id="bien" value="Bien" v-model="user.radio">
            <label>Bien</label>
          </div>
          <div>
            <input class="radio-selection" type="radio" name="radio-selected" id="muy bien" value="Muy bien" v-model="user.radio">
            <label>Muy bien</label>
          </div>
          <div>
            <input class="radio-selection" type="radio" name="radio-selected" id="increible" value="Increíble" v-model="user.radio">
            <label>Increíble</label>
          </div>
        </div>
      </div>
      <hr>
      <div class="leftForm-sections">
        <div>
          <label class="form-title">Competencias aprendidas: </label>
        </div>
        <div class="checkbox-section">
          <input v-model="user.check" name="competencias" type="checkbox" value="morfologia">
          Morfología de un componente
          <input v-model="user.check" name="competencias" type="checkbox" value="onetwo-way">
          One-Way y Two-way data binding
          <input v-model="user.check" name="competencias" type="checkbox" value="patron">
          El patrón de diseño MVVM
          <input v-model="user.check" name="competencias" type="checkbox" value="directivas">
          Directivas
          <input v-model="user.check" name="competencias" type="checkbox" value="estado">
          Estado
        </div>
      </div>
      <hr>
      <div class="leftForm-sections">
        <label class="form-title">Opinión:</label>
        <textarea v-model="user.opinion" class="textarea" name="comentarios" rows="4" cols="100" maxlength="280"
          placeholder="Escribe aquí tus comentarios"></textarea>
      </div>
    </form>
    <aside class="right-section">
      <table>
        <tr class="emoji-display">{{ user.emoji }}</tr><br>
        <tr>
          <h1>{{ user.title }}</h1><br>
        </tr>
        <tr><b>Y me parece {{ user.radio }}</b></tr><br>
        <tr><b>He aprendido : <br><br> {{ user.check }}</b></tr><br>
        <tr>
          <p><b>Mi opinión hasta ahora del framework es:</b></p><br>
          <div>{{ user.opinion }}</div>
        </tr>
      </table>
    </aside>
  </div>
</template>

<script>
export default {
  name: 'BindingDeUsuarios',
  data() {
    return {
      user: {
        title: "",
        emoji: "",
        radio: "",
        check: [],
        opinion: "",
      }
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex
}

.leftForm {
  background-color: rgba(0, 0, 0, 0.877);
  margin: 45px;
  padding: 1.5%;
  border-radius: 15px;
  width: 45%;
  height: 59vh;
  color: white;
}

.leftForm-sections {
  padding-top: 15px;
  padding-bottom: 15px;
  display: flex;
  align-items: center;
}

.form-title {
  font-size: 20px;
  padding: 0 15px 0 0;
}

.form-input {
  height: 25px;
  font-size: 18px;
}

.form-emoji {
  height: 30px;
  font-size: 20px;
}

.form-radio {
  display: flex;
  align-items: center;
  gap: 20px;
}

.radio-selection {
  margin-right: 10px;
}


.checkbox-section {
  display: flex;
  flex-direction: column;
}

.textarea {
  font-size: 18px;
}

.right-section {
  align-items: center;
  justify-content: center;
  margin: 45px;
  padding: 1.5%;
  width: 55%;
  height: 55vh;
  color: black;
  display: flex;
  flex-direction: column;
  border-style: solid 5px;
  border-color: black;
  font-size: 25px;
  color: #447294;
}

.emoji-display {
  font-size: 30px;
}

textarea {
  resize:none;
}
</style>
