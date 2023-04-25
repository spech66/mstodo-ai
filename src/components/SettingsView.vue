<template>
  <div class="settings">
    <h1>Settings</h1>
    <div class="settings__input">
      <label for="client-id">Client ID</label>
      <input type="text" id="client-id" v-model="clientId" />
    </div>
    <div class="settings__input">
      <label for="openai-api-key">OpenAI API Key</label>
      <input type="text" id="openai-api-key" v-model="openaiApiKey" />
    </div>
    <button @click="saveSettings">Save</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'SettingsView',
  setup() {
    const clientId = ref('')
    const openaiApiKey = ref('')

    const saveSettings = () => {
      localStorage.setItem('clientId', clientId.value)
      localStorage.setItem('openaiApiKey', openaiApiKey.value)
    }

    return {
      clientId,
      openaiApiKey,
      saveSettings,
    }
  },
});
</script>
