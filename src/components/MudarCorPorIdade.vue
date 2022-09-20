<template>
    <Message :msg=" msg" v-show="msg" />

    <form id="form" @submit="verify">
        <input v-bind:class="{ active: isActive }" type="number" placeholder="digite sua idade" v-model="age">
        <button>Verificar</button>
    </form>
</template>

<script>
import Message from './Message.vue';
export default {
    data() {
        return {
            age: 0,
            isActive: false,
            msg: null
        };
    },
    methods: {
        verify(e) {
            e.preventDefault();
            const data = {
                age: this.age,
                isActive: this.isActive
            };
            if (data.age < 18) {
                this.isActive = true
                setTimeout(() => this.isActive = false, 3000)
            }
            this.msg = `Idade: ${data.age}`
            setTimeout(() => this.msg = "", 3000)
        }
    },
    components: { Message }
}
</script>
<style>
.active {
    background-color: #dc5b60;
    border: #dc5b60;
}
</style>