<script setup>
import InputText from 'primevue/inputtext'
import Card from 'primevue/card'
import Button from 'primevue/button'
import axios from 'axios'
</script>

<template>
  <main>
    <Card style="min-width: 300px;text-align: center;">
      <template #title > Shorten URL </template>
      <template #content style="padding: 1.25rem 0;display: flex;flex-direction: column;gap: 10px;">
        <div style="
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            gap: 20px;
        ">
            <InputText placeholder="Search" v-model="url" />
          <Button style="margin-left: 1rem" @click="shorten" label="Shorten" rounded />
        </div>
        <Button v-if="show" link :label="shortenedUrl" @click="copy"/>
      </template>
    </Card>
  </main>
</template>
<script>
export default {
  data() {
    return {
      url: '',
      shortenedUrl: '',
      show: false
    }
  },
  methods: {
    async shorten() {
      this.show = true
      this.shortenedUrl = await (
        await axios.get(`https://api.shrtco.de/v2/shorten?url=${this.url}`)
      ).data.result.short_link
    },
    copy() {
      navigator.clipboard.writeText(this.shortenedUrl)
      alert("Copied to clipboard!");
    }
  }
}
</script>
