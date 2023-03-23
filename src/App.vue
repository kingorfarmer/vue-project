<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { ChevronDownIcon } from '@heroicons/vue/20/solid'
</script>

<template>
  <div class="container">
    <div class="w-full">
      <div class="text-[1.5rem]">Games</div>
      <div class="text-sm text-gray-500 mt-1">From sources across the web</div>
      <div class="mt-2 grid gap-x-20 grid-cols-3">
        <div v-for="n in 9" :key="n">
          <Disclosure v-slot="{ open }">
            <DisclosureButton
              :class="`flex w-full justify-between items-center py-2 text-left text-sm font-medium ${
                n === 7 || n === 8 || n === 9 ? '' : 'border-b'
              }`"
            >
              <div class="flex items-center">
                <img
                  src="./assets/grand-theft-auto-v-icon.jpg"
                  alt="game-icon"
                  width="58"
                  height="58"
                  class="rounded-lg"
                />
                <div class="ml-3">Grand Theft Auto V</div>
              </div>
              <ChevronDownIcon :class="open ? 'rotate-180 transform' : ''" class="h-6 w-6" />
            </DisclosureButton>
            <DisclosurePanel class="py-2 text-sm text-gray-500">
              If you're unhappy with your purchase for any reason, email us within 90 days and we'll
              refund you in full, no questions asked.
            </DisclosurePanel>
          </Disclosure>
        </div>
      </div>
    </div>
  </div>
</template>
