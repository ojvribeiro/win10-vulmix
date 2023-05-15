<script setup>
  import { useNow, useDateFormat } from '@vueuse/core'

  const formattedTime = useDateFormat(useNow(), 'HH:mm')
  const formattedDate = useDateFormat(useNow(), 'DD/MM/YYYY')
</script>

<template>
  <div
    class="fixed bottom-0 left-0 h-11 w-screen bg-zinc-900/90 font-light backdrop-blur-md"
  >
    <div class="flex h-full justify-between">
      <div class="flex h-full gap-[3px]">
        <div class="flex h-full">
          <ToolbarAppButton class="hover:text-green-300 active:text-green-500">
            <Icon icon="fa6-brands:windows" class="text-[19px]" />
          </ToolbarAppButton>

          <ToolbarSystemButton>
            <Icon
              icon="fluent:search-24-filled"
              :horizontalFlip="true"
              class="text-3xl"
            />
          </ToolbarSystemButton>

          <ToolbarTaskViewButton />
        </div>

        <div class="flex h-full">
          <ToolbarAppButton>
            <Icon icon="logos:chrome" class="text-2xl" />
          </ToolbarAppButton>

          <ToolbarAppButton>
            <Icon icon="vscode-icons:file-type-vscode" class="text-3xl" />
          </ToolbarAppButton>
        </div>
      </div>

      <div class="flex">
        <ToolbarTaskbarButton class="mr-2 px-3">
          <div class="flex items-center gap-1">
            <div class="text-3xl">
              <Icon icon="fluent-emoji:cloud-with-rain" />
            </div>

            <div class="flex gap-2 text-sm">
              <div>30°C</div>

              <div>Rainy</div>
            </div>
          </div>
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="px-1">
          <Icon icon="fluent-mdl2:chevron-up-med" class="text-sm" />
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="px-1">
          <Icon icon="fluent-mdl2:devices-3" class="text-[21px]" />
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="px-1">
          <Icon icon="fluent-mdl2:volume-3" />
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="px-2">
          <div class="space-y-1 text-xs">
            <div>{{ formattedTime }}</div>
            <div>{{ formattedDate }}</div>
          </div>
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="px-3">
          <Icon icon="fluent-mdl2:action-center" />
        </ToolbarTaskbarButton>

        <ToolbarTaskbarButton class="ml-2 w-[5px] border-l border-white/30">
          <span>&nbsp;</span>
        </ToolbarTaskbarButton>
      </div>
    </div>
  </div>
</template>
