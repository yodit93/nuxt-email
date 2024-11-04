<script setup>
    import { ref } from 'vue';
    import Sidebar from '~/components/Sidebar.vue';
    const emails = ref([
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "[JIRA] (LXQ-2604) Learning path- file - Existing File -two buttons for viewing the file", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "[JIRA] (LXQ-2604) Learning path- file - Existing File -two buttons for viewing the file", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "[JIRA] (LXQ-2604) Learning path- file - Existing File -two buttons for viewing the file", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "[JIRA] (LXQ-2604) Learning path- file - Existing File -two buttons for viewing the file", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "[JIRA] (LXQ-2604) Learning path- file - Existing File -two buttons for viewing the file", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        },
        {
            title: "Wave hello with video, reactions and more now in huddles", 
            body: "In the early days of the pandemic, audio-only huddles helped recreate the informal discussions that traditionally took place in office cafés and hallways. Whether your team is remote, in the office, or a mix of both, working alongside your colleagues is as important as ever."
        }
    ]); 
</script>
<template>
    <div class="container">
        <Sidebar />
        <div class="email-list-container">
            <h2>Archive</h2>
            <div class="select-email-cont">
                <div class="select-email">
                    <input type="checkbox">
                    <p>Emails selected (0)</p>
                </div>
            </div>
            <ul class="lists-cont">
                <li v-for="email in emails" :key="email.title" class="list">
                    <input type="checkbox">
                    <h3>{{ email.title }}</h3>
                </li>
            </ul>
        </div>
    </div>
    
    
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&family=Poppins:wght@400;800&display=swap');
    h2 {
        margin: 0 0 32px 0;
        padding-left: 24px;
        font-size: 32px;
    }
    li {
        list-style-type: none;
    }
    ul {
        padding: 0;
    }
    p {
        margin: 0;
    }
    p, h3 {
        font-size: 14px;
    }
    img {
        width: 19px;
        height: 19px;
    }
    button {
        border: none;
        background: none;
        display: flex;
        gap: 12px;
        align-items: center;
    }
    .container {
        display: flex;
    }
    .email-list-container {
        width: calc(100vw - 260px);
        font-family: 'Plus Jakarta Sans', sans-serif;
    }
    .select-email-cont {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-left: 24px;
    }
    .select-email {
        display: flex;
        gap: 12px;
    }
    .buttons-container {
        display: flex;
        gap: 40px;
    }
    .lists-cont {
        display: flex;
        flex-direction: column;
    }
    .list {
        display: flex;
        gap: 20px;
        border-top: 1px solid #E5E7EB;
        padding-left: 24px;
        color: #121829;

    }
    .list:hover {
        background-color: #F3F6FB;
    }

</style>