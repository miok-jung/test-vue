<template>
  <div>
    <!-- SECTION: 첫번째 방법 -->
    <q-list
      class="row no-wrap items-start q-ma-sm"
      style="height: calc(50vh - 50px)"
    >
      <!-- NOTE: Component1 -->
      <!-- expansion-item: header-style : 아코디언 제목의 CSS를 수정할 수 있다. 해당 아코디언의 클래스는 전체적으로 적용이 될 일반 class와, 아이콘 전용 클래스인 expand-icon-class 두가지로 될 수 있다.
      만약 group라는 속성값을 사용하여 같은 그룹으로 표기가 되면 하나만 열리게 된다.
      -->
      <q-expansion-item
        v-model="expandValues[0]"
        class="q-mr-sm bg-grey-3"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        :duration="0"
        style="
          overflow-x: hidden;
          height: calc(100% - 16px);
          transition: all 250ms;
        "
        :style="{
          width:
            expandValues[0] === true ? `calc(100% / ${expandCount})` : '50px',
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[0] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          width: expandValues[0] === true ? '100%' : '50px',
          alignItems: 'center',
        }"
      >
        <template #header> 가나다123ABC 11 </template>
        <TestComponent1 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
      <!-- NOTE: Component2 -->
      <q-expansion-item
        v-model="expandValues[1]"
        class="q-mr-sm bg-red-3"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        :duration="0"
        style="
          overflow-x: hidden;
          height: calc(100% - 16px);
          transition: all 250ms;
        "
        :style="{
          width:
            expandValues[1] === true ? `calc(100% / ${expandCount})` : '50px',
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[1] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          width: expandValues[1] === true ? '100%' : '50px',
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
        class="q-mr-sm bg-green-3"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        :duration="0"
        style="
          overflow-x: hidden;
          height: calc(100% - 16px);
          transition: all 250ms;
        "
        :style="{
          width:
            expandValues[2] === true ? `calc(100% / ${expandCount})` : '50px',
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[2] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          width: expandValues[2] === true ? '100%' : '50px',
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
        class="bg-grey-3"
        expand-icon-class="q-pr-none"
        expand-icon="mdi-chevron-right"
        :duration="0"
        style="
          overflow-x: hidden;
          height: calc(100% - 16px);
          transition: all 250ms;
        "
        :style="{
          width:
            expandValues[3] === true ? `calc(100% / ${expandCount})` : '50px',
          // 한글로 세로로 왼쪽에서 오른쪽으로 표기
          writingMode:
            expandValues[3] === true ? 'horizontal-tb' : 'vertical-lr',
          // 영어/숫자를 세로로 표기
          textOrientation: 'upright',
        }"
        :header-style="{
          width: expandValues[3] === true ? '100%' : '50px',
          alignItems: 'center',
        }"
      >
        <template #header>
          <p style="">가나다123ABC 44</p>
        </template>
        <TestComponent4 style="height: 100%; writing-mode: horizontal-tb" />
      </q-expansion-item>
    </q-list>
    <!-- !SECTION: 첫번째 방법 END -->
    <!-- SECTION: 두번재 방법 -->
    <q-list
      class="row no-wrap flex-start"
      style="height: calc(50vh - 50px); border: 1px solid red"
    >
      <div
        class="bg-grey-2 q-ml-sm q-my-sm"
        :class="expandValues[0] === true ? 'col' : ''"
      >
        <!-- NOTE: 제목 -->
        <div
          class="row items-center"
          :class="expandValues[0] === true ? 'reverse justify-between' : ''"
          :style="{
            // 한글로 세로로 왼쪽에서 오른쪽으로 표기
            writingMode:
              expandValues[0] === true ? 'horizontal-tb' : 'vertical-lr',
            // 영어/숫자를 세로로 표기
            textOrientation: 'upright',
          }"
          style="border: 1px solid red"
        >
          <q-btn
            :icon="
              expandValues[0] === true ? 'mdi-menu-left' : 'mdi-menu-right'
            "
            @click="changeExpandValue(0)"
          ></q-btn>
          <span>가나다AaBbCc1 1</span>
        </div>
        <!-- NOTE: 내용 -->
        <div v-if="expandValues[0] === true">
          <TestComponent1 />
        </div>
      </div>
      <div
        class="bg-green-3 q-ml-sm q-my-sm"
        :class="expandValues[1] === true ? 'col' : ''"
      >
        <!-- NOTE: 제목 -->
        <div
          :class="expandValues[1] === true ? 'reverse justify-between' : ''"
          :style="{
            // 한글로 세로로 왼쪽에서 오른쪽으로 표기
            writingMode:
              expandValues[1] === true ? 'horizontal-tb' : 'vertical-lr',
            // 영어/숫자를 세로로 표기
            textOrientation: 'upright',
          }"
        >
          <q-btn
            :icon="
              expandValues[1] === true ? 'mdi-menu-left' : 'mdi-menu-right'
            "
            @click="changeExpandValue(1)"
          ></q-btn>
          <span>가나다AaBbCc2 2</span>
        </div>
        <!-- NOTE: 내용 -->
        <div
          v-if="expandValues[1] === true"
          style="overflow-y: auto; height: calc(100% - 36px)"
        >
          <TestComponent2 />
        </div>
      </div>
      <div
        class="bg-orange-5 q-ml-sm q-my-sm"
        :class="expandValues[2] === true ? 'col' : ''"
      >
        <!-- NOTE: 제목 -->
        <div
          :class="expandValues[2] === true ? 'reverse justify-between' : ''"
          :style="{
            // 한글로 세로로 왼쪽에서 오른쪽으로 표기
            writingMode:
              expandValues[2] === true ? 'horizontal-tb' : 'vertical-lr',
            // 영어/숫자를 세로로 표기
            textOrientation: 'upright',
          }"
        >
          <q-btn
            :icon="
              expandValues[2] === true ? 'mdi-menu-left' : 'mdi-menu-right'
            "
            @click="changeExpandValue(2)"
          ></q-btn>
          <span>가나다AaBbCc3 3</span>
        </div>
        <!-- NOTE: 내용 -->
        <div v-if="expandValues[2] === true">
          <TestComponent3 />
        </div>
      </div>
      <div
        class="bg-grey q-ma-sm"
        :class="expandValues[3] === true ? 'col' : ''"
      >
        <!-- NOTE: 제목 -->
        <div
          :style="{
            // 한글로 세로로 왼쪽에서 오른쪽으로 표기
            writingMode:
              expandValues[3] === true ? 'horizontal-tb' : 'vertical-lr',
            // 영어/숫자를 세로로 표기
            textOrientation: 'upright',
          }"
        >
          <q-btn
            :icon="
              expandValues[3] === true ? 'mdi-menu-left' : 'mdi-menu-right'
            "
            @click="changeExpandValue(3)"
          ></q-btn>
          <span>가나다AaBbCc4 4</span>
        </div>
        <!-- NOTE: 내용 -->
        <div v-if="expandValues[3] === true">
          <TestComponent4 />
        </div>
      </div>
    </q-list>
    <!-- SECTION: 두번재 방법 END -->
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue';
import TestComponent1 from 'src/components/TestComponent1.vue';
import TestComponent2 from 'src/components/TestComponent2.vue';
import TestComponent3 from 'src/components/TestComponent3.vue';
import TestComponent4 from 'src/components/TestComponent4.vue';

const expandValues = ref<boolean[]>([false, false, false, false]);
const expandCount = ref<number>(0);

function changeExpandValue(index: number) {
  if (expandValues.value[index] === true) expandValues.value[index] = false;
  else expandValues.value[index] = true;
}

// NOTE: watch
watch(expandValues.value, () => {
  // 초기화 후 다시 카운팅
  expandCount.value = 0;
  expandValues.value.filter((val) => {
    if (val === true) expandCount.value += 1;
  });
});
</script>
<style scoped lang="scss">
.q-expansion-item {
  .q-focus-helper {
    visibility: hidden;
    transition: none;
  }
}
::v-deep(.q-item) {
  padding: 0;
}
</style>
