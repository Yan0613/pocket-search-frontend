<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.videoList"
    v-if="props.videoList"
  >
    <template #renderItem="{ item }">
      <a :href="item.url">
        <a-list-item>
          <a-card hoverable style="width: 150%">
            <template #cover>
              <img
                :src="item.pic"
                referrerpolicy="no-referrer"
                style="width: 100%; height: 100px; object-fit: cover"
              />
            </template>
            <a-card-meta :title="item.author" style="width: 100%; height: 80px">
              <template #description>
                <span
                  v-html="item.title"
                  style="width: 100%; height: 30px"
                ></span>
              </template>
            </a-card-meta>
          </a-card>
        </a-list-item>
      </a>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import wft from "../assets/gege.jpg";
import { withDefaults, defineProps } from "vue";

interface Props {
  videoList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  videoList: () => [],
});
</script>
