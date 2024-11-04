<script setup>
import { ref, computed } from 'vue';
import useEmailStore from '@/composables/useEmailStore';

// Fetch emails from the composable store or define them here.
const { inboxEmails, moveToArchive } = useEmailStore();

// Reactive state for selected emails
const selectedEmails = ref([]);

// Function to handle selection
const toggleSelectEmail = (email) => {
  if (selectedEmails.value.includes(email)) {
    selectedEmails.value = selectedEmails.value.filter((e) => e !== email);
  } else {
    selectedEmails.value.push(email);
  }
};

// Computed property to check if any email is selected
const isAnyEmailSelected = computed(() => selectedEmails.value.length > 0);

// Archive selected emails
const archiveSelectedEmails = () => {
  selectedEmails.value.forEach((email) => moveToArchive(email.id));
  inboxEmails.value = inboxEmails.value.filter((email) => !selectedEmails.value.includes(email));
  selectedEmails.value = [];
};

// Mark selected emails as read
const markAsRead = () => {
  selectedEmails.value.forEach((email) => {
    email.read = true; // Mark each selected email as read
  });
  selectedEmails.value = []; // Clear selection after marking as read
};
</script>


<template>
    <div class="container">
      <Sidebar />
      <div class="email-list-container">
        <h2>Inbox</h2>
  
        <!-- Selection and Actions Section -->
        <div class="select-email-cont">
          <div class="select-email">
            <input type="checkbox" @change="selectedEmails = $event.target.checked ? [...inboxEmails] : []" />
            <p>Emails selected ({{ selectedEmails.length }})</p>
          </div>
  
          <!-- Buttons appear only if any email is selected -->
          <div class="buttons-container" v-if="isAnyEmailSelected">
            <button type="button" @click="markAsRead">
              <img src="/assets/mail-04.png" alt="mail icon">
              <span>Mark as read (r)</span>
            </button>
            <button type="button" @click="archiveSelectedEmails">
              <img src="/assets/trash-01.png" alt="trash icon">
              <span>Archive (a)</span>
            </button>
          </div>
        </div>
  
        <!-- Email List Section -->
        <ul class="lists-cont">
          <li v-for="email in inboxEmails" :key="email.title" class="list">
            <input type="checkbox" @change="toggleSelectEmail(email)" />
            <h3 :class="{ 'read-email': email.read }">{{ email.title }}</h3>
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
    .read-email {
        font-weight: normal;
        color: #6c757d;
    }

</style>