<script>
  import settings from '@stores/settings';
  import { slide } from 'svelte/transition';
</script>

<div transition:slide>
  {#if $$slots.head}
    <div class="p-8 border-b {$settings.invertColors ? 'border-grey5inverse' : 'border-grey5'}">
      <div class="container mx-auto">
        <slot name="head" />
      </div>
    </div>
  {/if}
  {#if $$slots.message}
    <div class="container mx-auto lg:px-8 px-4 pt-8">
      <div
        class="border-y-1 py-2 rounded text-sm border border-green4 {$settings.invertColors
          ? 'bg-green7 text-white2inverse'
          : 'bg-black2 text-white2'} flex flex-row justify-center space-x-4"
      >
        <slot name="message" />
      </div>
    </div>
  {/if}
  <div class="px-4 pt-4 md:px-8 md:pt-8 pb-36">
    <div class="container flex flex-col  md:mx-auto">
      <slot />
    </div>
  </div>
</div>
