<script lang="ts" setup>
import "cropperjs/dist/cropper.css";
import Cropper from "cropperjs";

const props = defineProps<{
  id: string;
  src: string;
}>();

tryOnMounted(() => {
  new Cropper(<HTMLImageElement>document.getElementById(props.id), {
    dragMode: "move",
    aspectRatio: 1.58,
    autoCropArea: 0.65,
    cropBoxMovable: false,
    cropBoxResizable: false,
    toggleDragModeOnDblclick: false,
  });
});
</script>

<template>
  <CardLayout style="max-width: 640px">
    <div>
      <img :id="id" :src="src" alt="Input Image" style="max-width: 100%" />
    </div>
  </CardLayout>
</template>
