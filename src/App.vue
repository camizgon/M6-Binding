<template>
  <div id="app">
    <div class="form-container card">
      <!--Formulario-->
      <form>
        <!-- Grupo de Título -->
        <div class="form-group">
          <label for="title">Título:</label>
          <input type="text" id="title" v-model="title">
        </div>
        
        <!--Linea separadora-->
        <hr class="separator">

        <!-- Grupo de Emoji -->
        <div class="form-group">
          <label for="emoji">Emoji:</label>
          <select id="emoji" v-model="emoji">
            <option value="😊">😊</option>
            <option value="😢">😢</option>
            <option value="😠">😠</option>
          </select>
        </div>

        <!--Linea separadora-->
        <hr class="separator">

        <!-- Grupo de Apreciación -->
        <div class="form-group">
          <label>Apreciación:</label>
          <div class="radio-group">
            <div>
              <input type="radio" id="regular" value="Regular" v-model="appreciation">
              <label for="regular">Regular</label>
            </div>
            <div>
              <input type="radio" id="good" value="Bien" v-model="appreciation">
              <label for="good">Bien</label>
            </div>
            <div>
              <input type="radio" id="very-good" value="Muy bien" v-model="appreciation">
              <label for="very-good">Muy bien</label>
            </div>
            <div>
              <input type="radio" id="excellent" value="Increíble" v-model="appreciation">
              <label for="excellent">Increíble</label>
            </div>
          </div>
        </div>

        <!--Linea separadora-->
        <hr class="separator">

        <div class="form-group">
          <!-- Grupo de Competencias -->
          <label>Competencias:</label>
          <div class="checkbox-group">
            <div>
              <input type="checkbox" id="competence1" value="Morfología de un componente" v-model="competences">
              <label for="competence1">Morfología de un componente</label>
            </div>
            <div>
              <input type="checkbox" id="competence2" value="One-Way y Two-Way data binding" v-model="competences">
              <label for="competence2">One-Way y Two-Way data binding</label>
            </div>
            <div>
              <input type="checkbox" id="competence3" value="El patrón de diseño MVVM" v-model="competences">
              <label for="competence3">El patrón de diseño MVVM</label>
            </div>
            <div>
              <input type="checkbox" id="competence4" value="Directivas" v-model="competences">
              <label for="competence4">Directivas</label>
            </div>
            <div>
              <input type="checkbox" id="competence5" value="Estado" v-model="competences">
              <label for="competence5">Estado</label>
            </div>
          </div>
        </div>

        <!--Linea separadora-->
        <hr class="separator">

        <!--Grupo Opinión-->
        <div class="form-group">
          <label for="opinion">Opinión:</label>
          <textarea id="opinion" v-model="opinion"></textarea>
        </div>
      </form>
    </div>

    <!--Interpolación vista previa de la salida-->
    <div class="output-container card">
      <h2>Vista previa</h2>
      <p><strong>Título:</strong> {{ title }}</p>
      <p><strong>Emoji:</strong> {{ emoji }}</p>
      <p><strong>Apreciación:</strong> {{ appreciation }}</p>
      <p><strong>Competencias:</strong> {{ competences.join(', ') }}</p>
      <p><strong>Opinión:</strong> {{ opinion }}</p>
    </div>
  </div>
</template>

<!--Declaración de variables-->
<script>
export default {
  data() {
    return {
      title: '',
      emoji: '',
      appreciation: '',
      competences: [],
      opinion: ''
    };
  }
};
</script>
<!--Me apoye en los estilos con ChatGPT, habian cositas que me costo darles diseño-->
<!--Estilos-->
<style>
#app {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  font-family: Arial, sans-serif;
}

.card {
  border: 2px solid #333;
  padding: 20px;
  border-radius: 10px;
}

.form-container {
  width: 45%;
  background-color: #000;
  color: #fff;
  padding: 20px;
}

.output-container {
  width: 45%;
  background-color: #f0f0f0;
  padding: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 10px;
}

label {
  font-weight: bold;
  margin-bottom: 5px;
  display: block;
}

input[type="text"],
select,
textarea {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  box-sizing: border-box;
  border-radius: 5px;
}

select#emoji {
  width: 50px;
  padding: 5px;
  text-align: center;
}

input[type="radio"],
input[type="checkbox"] {
  margin-right: 10px;
}

textarea {
  height: 100px;
}

h2 {
  border-bottom: 2px solid #333;
  padding-bottom: 5px;
}

.output-container p {
  font-size: 16px;
  margin: 10px 0;
}

.output-container strong {
  color: #555;
}

.radio-group {
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

.checkbox-group {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.separator {
  border: 0;
  border-top: 1px solid #fff;
  margin: 10px 0;
}
</style>
