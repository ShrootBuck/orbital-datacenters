<script setup>
import { useNav } from '@slidev/client'
import { computed, unref } from 'vue'
const nav = useNav()
const page = computed(() => unref(nav.currentPage))
</script>
<template><div class="rail">ORBITAL / INVESTMENT BRIEF</div><div class="slide-no">{{ String(page).padStart(2,'0') }} <span style="color:#53677d">/ {{ page > 13 ? 'APPENDIX' : '13' }}</span></div><div class="bottom-line" :style="{width:Math.min(page/13*100,100)+'%'}" /></template>
