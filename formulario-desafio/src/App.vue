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
				
				<NomeCompleto v-model="nomeCompleto"/>

				<Rotulo nome="Email">
					<input type="email" name="email" id="email" v-model="email">
				</Rotulo>
				<Rotulo nome="Senha">
					<input type="password" name="senha" id="senha" v-model="senha">
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
				<Rotulo  nome="Nome">
					<span>{{ nomeCompleto.nome }}</span>
				</Rotulo>
				<Rotulo  nome="Sobrenome">
					<span>{{ nomeCompleto.sobrenome }}</span>
				</Rotulo>
				<Rotulo nome="Email">
					<span>{{ email }}</span>
				</Rotulo>
				<Rotulo nome="Senha">
					<span>{{ senha }}</span>
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
import NomeCompleto from './components/NomeCompleto.vue'

export default {
	name: 'app',
	components: { NomeCompleto, Rotulo },
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
			nomeCompleto: {
				nome: '',
				sobrenome: ''
			},
			email: '',
			senha: '',
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
