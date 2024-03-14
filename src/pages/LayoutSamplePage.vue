<template>
  <div>
    <q-list class="row no-wrap flex-start" style="height: calc(100vh - 50px)">
      <!-- NOTE: Component1 -->
      <!-- expansion-item: header-style : 아코디언 제목의 CSS를 수정할 수 있다. 해당 아코디언의 클래스는 전체적으로 적용이 될 일반 class와, 아이콘 전용 클래스인 expand-icon-class 두가지로 될 수 있다. -->
      <q-expansion-item
        v-model="expandValues[0]"
        class="q-ml-sm q-my-sm bg-grey-3"
        :class="expandValues[0] === true ? 'col' : ''"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        style="height: calc(100% - 16px)"
        :duration="0"
        :style="{
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[0] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          padding: expandValues[0] === true ? '' : '16px 8px',
          alignItems: 'center',
        }"
      >
        <template #header>
          <p style="">가나다123ABC 11</p>
        </template>
        <TestComponent1 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
      <!-- NOTE: Component2 -->
      <q-expansion-item
        v-model="expandValues[1]"
        class="q-ml-sm q-my-sm bg-red-3"
        :class="expandValues[1] === true ? 'col' : ''"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        style="height: calc(100% - 16px)"
        :duration="0"
        :style="{
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[1] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          padding: expandValues[1] === true ? '' : '16px 8px',
          alignItems: 'center',
        }"
      >
        <template #header>
          <p style="">가나다123ABC 22</p>
        </template>
        <TestComponent2 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
      <!-- NOTE: Component3 -->
      <q-expansion-item
        v-model="expandValues[2]"
        class="q-ml-sm q-my-sm bg-green-3"
        :class="expandValues[2] === true ? 'col' : ''"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        style="height: calc(100% - 16px)"
        :duration="0"
        :style="{
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[2] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          padding: expandValues[2] === true ? '' : '16px 8px',
          alignItems: 'center',
        }"
      >
        <template #header>
          <p style="">가나다123ABC 33</p>
        </template>
        <TestComponent3 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
      <!-- NOTE: Component4 -->
      <q-expansion-item
        v-model="expandValues[3]"
        class="q-ma-sm bg-grey-3"
        :class="expandValues[3] === true ? 'col' : ''"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        style="height: calc(100% - 16px)"
        :duration="0"
        :style="{
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[3] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          padding: expandValues[3] === true ? '' : '16px 8px',
          alignItems: 'center',
        }"
      >
        <template #header>
          <p style="">가나다123ABC 44</p>
        </template>
        <TestComponent4 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
    </q-list>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import TestComponent1 from 'src/components/TestComponent1.vue';
import TestComponent2 from 'src/components/TestComponent2.vue';
import TestComponent3 from 'src/components/TestComponent3.vue';
import TestComponent4 from 'src/components/TestComponent4.vue';

const expandValues = ref<boolean[]>([false, false, false, false]);
</script>
<style scoped lang="scss"></style>
