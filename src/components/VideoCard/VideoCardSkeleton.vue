<script setup lang="ts">
const props = defineProps<{
  horizontal?: boolean
  hasTag?: boolean
}>()

const wValue = computed((): string => {
  if (props.horizontal)
    return 'xl:280px lg:250px md:200px 200px'
  else
    return 'w-full'
})
</script>

<template>
  <div
    v-if="!horizontal"
    mb-6 pointer-events-none select-none
  >
    <div aspect-video bg="$bew-fill-4" rounded="$bew-radius" />
    <div flex mt-4>
      <div
        m="r-4" w="40px" h="40px" rounded="1/2" bg="$bew-fill-4"
        shrink-0
      />
      <div w-full>
        <div grid gap-2>
          <div w-full h-5 bg="$bew-fill-3" />
          <div w="3/4" h-5 bg="$bew-fill-3" />
        </div>
        <div grid gap-2 mt-4>
          <div w="50%" h-4 bg="$bew-fill-2" />
          <div w="80%" h-4 bg="$bew-fill-2" />
        </div>
        <div
          text="transparent sm" inline-block mt-4 p="x-2 y-1" bg="$bew-fill-1"
          rounded-4
        >
          hello world
        </div>
      </div>
    </div>
  </div>

  <div
    v-else
    flex="~ gap-6"
    mb-6 pointer-events-none select-none
  >
    <!-- By directly using predefined unocss width properties, it is possible to dynamically set the width attribute -->
    <div hidden w="xl:280px lg:250px md:200px 200px" />
    <div hidden w="full" />

    <!-- Cover -->
    <div
      :w="wValue" shrink-0 aspect-video h-fit bg="$bew-fill-4"
      rounded="$bew-radius"
    />
    <!-- Other Information -->
    <div
      w-full mt-0
      flex="~ gap-4"
    >
      <div w-full>
        <div grid gap-2>
          <div w-full h-5 bg="$bew-fill-3" />
          <div w="3/4" h-5 bg="$bew-fill-3" />
        </div>
        <div grid gap-2 mt-4>
          <div :style="{ width: '70%' }" h-4 bg="$bew-fill-2" />
          <div w="80%" h-4 bg="$bew-fill-2" />
        </div>

        <div mt-4 flex>
          <div text="transparent sm" inline-block p="x-2 y-1" bg="$bew-fill-1" rounded-4>
            hello world
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
