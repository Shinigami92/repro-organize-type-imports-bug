<script lang="ts">
import type { InjectionKey, Ref } from "vue";

export interface TestProps {
  test?: string;
}

export const INJECTION_KEY_TEST: InjectionKey<Ref<string[]>> = Symbol("test");
</script>

<script setup lang="ts">
import { provide, ref } from "vue";

const props = withDefaults(defineProps<TestProps>(), {});

const test2: Ref<string[]> = ref([]);

provide(INJECTION_KEY_TEST, test2);
</script>
