<script lang="ts" setup></script>

<template>
  <q-drawer behavior="desktop" elevated overlay>
    <q-scroll-area class="fit">
      <q-list>
        <q-item v-for="i in $routeChildrenMain" :key="i.path" v-ripple :to="i.path" clickable exact>
          <q-item-section v-if="i.meta?.icon" avatar>
            <q-icon :name="i.meta.icon" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ i.meta.title }}</q-item-label>
            <q-item-label v-if="i.meta?.caption" caption>{{ i.meta.caption }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-scroll-area>
  </q-drawer>
</template>
