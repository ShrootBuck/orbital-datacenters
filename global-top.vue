<script setup>
import { useNav } from '@slidev/client'
import { computed, unref } from 'vue'
const nav = useNav()
const page = computed(() => unref(nav.currentPage))
</script>
<template><div class="slide-no">{{ String(page).padStart(2,'0') }} <span style="color:#53677d">/ 11</span></div><div class="bottom-line" :style="{width:Math.min(page/11*100,100)+'%'}" /></template>
