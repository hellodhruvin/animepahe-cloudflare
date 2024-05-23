<template>
  <div>
    <ClientOnly>
      <div class="container mx-auto p-4">
        <slot />
      </div>
      <!-- Content -->
      <template #fallback>
        <FallbackLoader />
      </template>
    </ClientOnly>
  </div>
</template>
