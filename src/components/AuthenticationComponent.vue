<template>
    <div>
        <h2>Аутентификация</h2>
            <div v-if="isAuthenticated">
                <p>Успешная аутентификация! Добро пожаловать!</p>
            </div>
            <div v-else>
                <form v-if="!isAuthenticated" @submit="login">
                    <label for="username">Имя пользователя:</label>
                    <input type="text" id="username" v-model="username" required>
                    <label for="password">Пароль:</label>
                    <input type="password" id="password" v-model="password" required>
                    <button type="submit">Войти</button>
                </form>
            </div>
    </div>
</template>

<script>
export default {
    name: 'AuthenticationComponent',
    data() {
        return {
            username: '',
            password: '',
            isAuthenticated: false,
            users: [
                    {username: 'sergey', password: 'admin'},
                    {username: 'admin', password: 'admin'},
                    {username: 'test', password: 'test'}
            ]
        }
    },
    methods: {
        login(event) {
            event.preventDefault();
            if (this.users.find(item => item.username === this.username && item.password === this.password)) {
                this.isAuthenticated = !this.isAuthenticated;
            }
            this.username = '';
            this.password = '';
        }
    }
};
</script>