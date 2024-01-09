<script setup>
const { locale } = useI18n()
</script>

<template>
  <div>
    <form>
      <select v-model="locale">
        <option value="en">en</option>
        <option value="fr">fr</option>
        <option value="cz">cz</option>
      </select>
    </form>
    <p>{{ $t('welcome') }}</p>
    <p>{{ $t('sayhallo') }}</p>
  </div>
</template>
