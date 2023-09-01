<template>
    <div>
        <p>{{ changeText }}</p>
        <button @click="togglePeriod">{{ buttonText }}</button>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue';


const period = ref('day')
const changeText = ref('Change per {{ day }}')


const buttonText = computed(() => {
    return period.value === 'day' ? 'Month' : 'Year';
});

// Функція для зміни періоду та тексту
function togglePeriod() {
    if (period.value === 'day') {
        changeText.value = 'Change per {{ Month }}';
        period.value = 'Month';
    } else {
        if (changeText.value.includes('Year')) {
            changeText.value = changeText.value.replace('Change per {{ Year }}', 'Change per {{ day }}');
        } else {
            changeText.value = changeText.value.replace('Change per {{ Month }}', 'Change per {{ day }}');
        }
        period.value = 'day';
    }
}

</script>