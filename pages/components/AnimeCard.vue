<template>
  <div
    class="card w-80 bg-base-100 border border-primary border-opacity-10 hover:border-opacity-30"
  >
    <figure>
      <NuxtImg
        format="png"
        :placeholder="
          NxtImg('/pahe.png', { h: 384, f: 'png', blur: 10, q: 50 })
        "
        :src="Prox(API, poster)"
        alt="Loading Poster..."
        class="h-96 rounded-md"
      />
    </figure>
    <div class="card-body justify-between p-6">
      <div class="flex flex-col">
        <div class="flex gap-2">
          <div class="badge badge-secondary font-medium text-white">
            {{ type }}
          </div>
          <div class="badge badge-primary font-medium text-white">
            EP {{ episodes }}
          </div>
          <div class="badge badge-accent font-medium">{{ status }}</div>
        </div>
        <h2 class="card-title text-ellipsis">{{ title }}</h2>
      </div>
      <div class="flex flex-col gap-2">
        <div class="card-actions">
          <div class="badge badge-neutral font-medium">{{ year }}</div>
          <div class="badge badge-neutral font-medium">{{ score }}</div>
          <div class="badge badge-neutral font-medium">{{ season }}</div>
        </div>
        <button
          @click="emit('onAnimeSelect', session)"
          type="submit"
          class="btn btn-outline btn-primary bg-base-300 text-base align-middle"
        >
          Download
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { Prox } from "~/composables/ImgProxy";
const {
  public: { API },
} = useRuntimeConfig();
const NxtImg = useImage();
const emit = defineEmits(["onAnimeSelect"]);
const { poster, type, episodes, status, title, year, score, season, session } =
  defineProps([
    "poster",
    "type",
    "episodes",
    "status",
    "title",
    "year",
    "score",
    "season",
    "session",
  ]);
</script>
