<script>
    export default {
        mounted() {
        if (localStorage.getItem('theme')) {
            document.documentElement.setAttribute('data-theme', localStorage.getItem('theme'));
        }else{
            localStorage.setItem('theme', 'light');
            document.documentElement.setAttribute('data-theme', 'light');
        }
    },
    methods: {
        toggleTheme() {
        const currentTheme = localStorage.getItem('theme');
        const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
        localStorage.setItem('theme', newTheme);
        document.documentElement.setAttribute('data-theme', newTheme);
        }
    }
};
</script>

<template>
    <div>
        <button class="themeButton" @click="toggleTheme" aria-label="Toggle theme" >Cambiar tema</button>
    </div>
</template>

<style>
:root {
    --bg-color: #ffffff;
    --text-color: #000000;
    --card-bg-color: #f0f0f0;
}

[data-theme="dark"] {
    --bg-color: #121212;
    --text-color: #ffffff;
    --card-bg-color: #212121;
}

body {
    background-color: var(--bg-color);
    color: var(--text-color);
    transition: background-color 0.3s ease, color 0.3s ease; /* Transición suave */
}

h1 {
    color: var(--text-color);
    background-color: var(--bg-color);
    transition: background-color 0.3s ease, color 0.3s ease;;
}

.themeButton {
    background-color: var(--card-bg-color);
    color: var(--text-color);
    border: 1px solid var(--text-color);
    border-radius: 10px;
    margin: 10px 80px 20px;
    cursor: pointer;
    transition: background-color 0.3s ease, color 0.3s ease;
    position: relative;
    bottom: 235px; left: 870px;
}
</style>