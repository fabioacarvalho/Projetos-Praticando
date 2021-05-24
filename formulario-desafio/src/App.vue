<template>
	<div id="app">
						<!-- FORMULARIO -->
		<h1>Formulário Desafio</h1>
		<div class="conteudo">
			<form class="painel" v-if="!enviado">
				<div class="cabecalho">Formulário</div>
				<!-- Exercicio 01 -->
				<!-- Criar uma formulário de registro -->
				<!-- Nome completo (Nome e Sobrenome) -->
				<!-- Email -->
				<!-- Senha -->
				<!-- Armazenar Dados? (Sim/Não) -->
				
				<Rotulo  nome="Nome">
					<input type="text" v-model="usuario.nome">
				</Rotulo>

				<Rotulo nome="Sobrenome">
					<input type="text" v-model="usuario.sobrenome">
				</Rotulo>

				<Rotulo nome="Email">
					<input type="email" name="email" id="email" v-model="usuario.email">
				</Rotulo>
				<Rotulo nome="Senha">
					<input type="password" name="senha" id="senha" v-model="usuario.senha">
				</Rotulo>
				<Rotulo nome="Armazenar Dados">
					<span><input type="radio" value="Sim" name="sim" id="sim" v-model="armazenar">Sim</span>
					<span><input type="radio" value="Não" name="nao" id="nao" v-model="armazenar">Não</span>
				</Rotulo>
				<hr>
				<button @click.prevent="enviar">Enviar</button>
				

				<!-- Exercicio 02 -->
				<!-- Só mostrar o fomulário de não tiver sido submetido -->
				<!-- Mostrar a área de Resultado apenas quando o formulário for submetido -->

			
				<!-- Exercicio 03 -->
				<!-- Crie um componente personalizado NomeCompleto -->
				<!-- Esse componente deve receber Nome e Sobrenome -->

				<!-- RESULTADO -->

			</form>
			<div class="painel" v-else>
				<div class="cabecalho">Resultado</div>
				<Rotulo  nome="Nome e Sobrenome">
					<span>{{ usuario.nome }} {{ usuario.sobrenome }}</span>
				</Rotulo>
				<Rotulo nome="Email">
					<span>{{ usuario.email }}</span>
				</Rotulo>
				<Rotulo nome="Senha">
					<span>{{ usuario.senha }}</span>
				</Rotulo>
				<Rotulo nome="Armazenar Dados">
					<span>
						{{ armazenar }}
					</span>
				</Rotulo>
				<hr>
				<button @click="reload">Novo</button>
			</div>
		</div>
	</div>
</template>

<script>
import Rotulo from './components/Rotulo.vue'

export default {
	name: 'app',
	components: { Rotulo },
	methods: {
		enviar() {
			this.enviado = true
		},
		reload () {
			window.location=document.URL			
		}
	},
	data() {
		return {
			armazenar: 'Sim',
			usuario: {
				nome: '',
				sobrenome: '',
				email: '',
				senha: ''
			},
			enviado: false,
		}
	}
}
</script>

<style>

body {
	background-color: #ECECEC;
}

#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;

	display: flex;
	flex-direction: column;
}

.conteudo {
	display: flex;
}

.painel {
	flex: 1;
	background: #FFF;
	margin: 0px 10px;
	padding: 20px;
	border: 1px solid #AAA;
	border-radius: 5px;
}

.painel .cabecalho {
	width: 100%;
	background-color: #DDD;
	padding: 10px 0px;
	border-radius: 5px;
	font-size: 1.4rem;
}

#app form button {
	float: right;
	margin: 10px 0px;
	padding: 10px 20px;
	font-size: 1.4rem;
	border-radius: 5px;
	color: #FFF;
	background-color: #2196F3;
}

#app div button {
	float: right;
	margin: 10px 0px;
	padding: 10px 20px;
	font-size: 1.4rem;
	border-radius: 5px;
	color: #FFF;
	background-color: #2196F3;
}

#app h1 {
	font-weight: 200;
	margin: 20px;
	padding: 0;
}

.mr-4 {
	margin-right: 40px;
}
</style>
