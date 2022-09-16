<template>
    <section>
        <strong class="display">{{ temposDecorrido }}</strong>
    </section>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
    name: "Cronometro",
    props: {
        tempoSegundos: {
            type: Number,
            default: 0,
        },
    },
    computed: {
        temposDecorrido(): string {
            return new Date(this.tempoSegundos * 1000)
                .toISOString()
                .substr(11, 8);
        },
    },
});
</script>
<style>
.display {
    color: var(--texto-primario);
}
</style>