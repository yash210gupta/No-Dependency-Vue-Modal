<template>
  <div id="app">
      <div class="al centerit">
			<img style="width:30vw;height:40vh" src="./assets/asset.png">
			<div class="al title">Click Here.</div>
			<div class="al body">Please click here<br/> to comment.</div>
			<button type="button" class="mybutton" @click="openAlert()">Comment</button>
			<br><br>
      </div>
      <modal ref="mymodal">
        <p>Add a comment</p>
        <form @submit.prevent>
          <textarea v-model.trim="comment"></textarea>
          <br><br>
          <button :disabled="comment == ''" class="mybutton">Add Comment</button>
        </form>
      </modal>
  </div>
</template>

<script>
import modal from './modal.vue'
 
export default {
  name: 'App',
   data: function () {
    return {
      comment:''
    }
  },
  components: {
    modal
  },
  methods:
  {
     openAlert()
     {
        this.$refs.mymodal.show();
     }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.al.title{
padding-top: 2%;
font-size: medium;
font-size: 28px;
font-family: lato;
letter-spacing: 0;
color: #474747;
text-transform: capitalize;
opacity: 1;
}
.al.centerit{
    text-align: center;
}
.al.body{
font-size: medium;
font-size: 20px;
font-family: lato;
letter-spacing: 0;
color: #707070;
opacity: 1; 
padding-bottom: 5%;
}
.spl-btn-login{
    background: white 0% 0% no-repeat padding-box;
    border: 1px solid #047B45;
    border-radius: 27px;
    color:#047B45;
    height: 30px;
    font-family: lato;
    font-size: 14px;
  }
  .spl-btn-login:hover{
    background: transparent linear-gradient(180deg, #0D7244 0%, #1F488E 100%) 0% 0% no-repeat padding-box;
    cursor: pointer;
    color: white;
}
.mybutton {
	background: #30A0EE;
	border: 0;
	outline: 0;
	color: #fff;
	padding: 0.8rem 1rem;
	min-width: 100px;
	font-size: 12px;
	border-radius: 3px;
	cursor: pointer;
}

.mybutton:hover {
	background: #48abf0;
}
p {
	line-height: 1.5;
}

a {
	font-family: 'Open Sans', sans-serif;
	text-decoration: none;
	color: #30A0EE;
	margin: 0;
	cursor: pointer;
}

a:hover {
	color: #48abf0;
}
form input {
	display: block;
	width: 100%;
	margin-bottom: 1rem;
	font-size: 16px;
	padding: 10px;
	outline: 0;
	border: 1px solid #e6ecf0;
	border-radius: 3px;
}

form input:focus {
	box-shadow: 0 0 5px 0 rgba(52, 73, 94, 0.2);
}

form textarea {
	resize: none;
	border: 1px solid #e6ecf0;
	outline: 0;
	height: 100px;
	width: 100%;
	padding: 10px;
	font-size: 16px;
}
button:hover{
  cursor:pointer;
}
</style>
