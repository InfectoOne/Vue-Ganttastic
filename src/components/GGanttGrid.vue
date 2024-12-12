<template>
  <div class="g-grid-container">
    <div
      v-for="({ label, date, width }, index) in timeaxisUnits.lowerUnits"
      :key="`${label}_${index}`"
      class="g-grid-line"
      :style="{
        width,
        background: shouldHighlight(date) ? colors.hoverHighlight : undefined
      }"
    />
  </div>
</template>

<script setup lang="ts">
import provideConfig from "../provider/provideConfig.js"
import useTimeaxisUnits from "../composables/useTimeaxisUnits.js"

const props = defineProps<{
  highlightedUnits?: number[]
}>()

const { colors, precision, highlightedDaysOfWeek, highlightedDates, highlightedHours } = provideConfig()
const { timeaxisUnits } = useTimeaxisUnits()

function shouldHighlight(date: Date): boolean {
  if (precision.value === "hour") {
    return highlightedHours?.value.includes(date.getHours())
  } else if (precision.value !== "week" && precision.value !== "month") {
    if (highlightedDaysOfWeek?.value.includes(date.getDay())) {
      return true
    }
    if (highlightedDates?.value.includes(date.getDate())) {
      return true
    }
    if (props.highlightedUnits?.includes(date.getHours())) {
      return true
    }
  }

  return false
}
</script>

<style>
.g-grid-container {
  position: absolute;
  top: 0;
  left: 0%;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
}

.g-grid-line {
  width: 1px;
  height: 100%;
  border-left: 1px solid #eaeaea;
}
</style>
