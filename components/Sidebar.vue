<script setup>

</script>
<template>
    <div class="sidebar-cont">
        <div class="top-part">
            <img class="logo" src="/public/assets/Logo.png" alt="logo">
            <nuxt-link to="/" exact-active-class="exact-active">
                <div class="left-part">
                    <img src="/public/assets/inbox-01.png" alt="mail icon">
                    <span>Inbox</span>
                </div>
                <span class="count">12</span>
            </nuxt-link>
            <nuxt-link to="/archive" exact-active-class="exact-active">
                <div class="left-part">
                    <img src="/public/assets/archive.png" alt="archive icon">
                    <span>Archive</span>
                </div>
                <span class="count">8</span>
            </nuxt-link>
        </div>
        <button class="logout">
            <img src="/public/assets/log-out-04.png" alt="logout icon">
            <span>Logout</span>
        </button>
    </div>
</template>
<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&family=Poppins:wght@400;800&display=swap');
    .sidebar-cont {
        width: 260px;
        height: 791px;
        padding: 20px 0px 20px 0px;
        border-right: 1px solid #E5E7EB;
        background-color:#F8FAFC;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
    }
    .top-part {
        display: flex;
        flex-direction: column;
        gap: 32px;
    }
    img {
        width: 24px;
        height: 24px;
    }
    .logo {
        width: 40px;
        height: 20px;
        align-self: flex-start;
        margin-left: 14px;   
    }
    .left-part {
        display: flex;
        align-items: center;
        gap: 12px;
        font-family: 'Plus Jakarta Sans', sans-serif;
    }
    a, button {
        border: none;
        box-sizing: border-box;
        width: 240px;
        height: 48px;
        display: flex;
        padding: 0px 24px;
        align-items: center;
        justify-content: space-between;
        cursor: pointer;
        border-radius: 54px;
        text-decoration: none;
        color: black;
    }
    .exact-active {
        background-color: #D6E2FB;
    }

    .logout {
       justify-content: left;
       gap: 12px; 
    }
</style>
