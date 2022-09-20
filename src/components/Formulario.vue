<template>
    <div>
        <Message :msg="msg" v-show="msg" />
        <p>Formulario</p>
        <div>
            <form id="form" @submit="mensagem">
                <div class="input-container">
                    <label for="nome">Nome do cliente</label>
                    <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite seu nome">
                </div>
                <div class="input-container">
                    <label for="dataNasc">dataNasc do cliente</label>
                    <input type="text" id="dataNasc" name="dataNasc" v-model="dataNasc"
                        placeholder="Digite seu Data de nascimento">
                </div>
                <div class="input-container">
                    <label for="sexo">sexo do cliente</label>
                    <select id="sexo" name="sexo" v-model="sexo">
                        <option value=""> Selecione o seu sexo</option>
                        <option value="Femino"> Feminino</option>
                        <option value="Masculino"> Masculino</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="nomePai">nomePai do cliente</label>
                    <input type="text" id="nomePai" name="nomePai" v-model="nomePai" placeholder="Digite seu nomePai">
                </div>
                <div class="input-container">
                    <label for="nomeMae">nomeMae do cliente</label>
                    <input type="text" id="nomeMae" name="nomeMae" v-model="nomeMae" placeholder="Digite seu nomeMae">
                </div>
                <div class="input-container">
                    <label for="profissao">profissao do cliente</label>
                    <input type="text" id="profissao" name="profissao" v-model="profissao"
                        placeholder="Digite seu profissao">
                </div>
                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Cardastrar">
                </div>
            </form>
        </div>
    </div>

</template>
<script>
import Message from './Message.vue';

export default {
    name: "FormularioForm",
    data() {
        return {
            nome: null,
            sexo: [],
            nomePai: null,
            nomeMae: null,
            profissao: null,
            dataNasc: null,
            msg: null,
        }
    },
    methods: {
        mensagem(e) {
            e.preventDefault();

            const data = {
                nome: this.nome,
                sexo: this.sexo,
                nomePai: this.nomePai,
                nomeMae: this.nomeMae,
                profissao: this.profissao,
                dataNasc: this.dataNasc
            }
            if (data.nome == 'thiago') {
                this.msg = "Cadastro realizado"
            } else {
                this.msg2 = "Cadastro realizado"
            }

            setTimeout(() => this.msg = "", 3000)
            setTimeout(() => this.msg2 = "", 3000)

            console.log(data)
        }
    },
    components: {
        Message
    }
}

</script>

<style scoped>
#form {
    max-width: 300px;
    margin: 0 auto;
}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 10px;
}

label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #fcba03;
}

input,
select {
    padding: 5px 10px;
    width: 300px;
}

.submit-btn {
    background-color: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
}

.submit-btn:hover {
    background-color: transparent;
    color: #222;

}
</style>