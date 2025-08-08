<script setup lang="ts">
import { useI18n } from '#imports'
import { config } from '~/config'
import AboutCard from '../Cards/AboutCard.vue'
import List from '../List/List.vue'
import ListItem from '../List/ListItem.vue'
import BaseSection from './BaseSection.vue'
import { useAnimationConfig } from '~/composables/useAnimationConfig'

const { t } = useI18n()
const { slideUp, delayed } = useAnimationConfig()
</script>

<template>
  <BaseSection id="about" :title="t('about.title')">
    <AboutCard
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 100)"
      :title="t('about.whatWeDo.title')"
      class="leading-relaxed"
    >
      <p class="text-muted-foreground mb-4">
        {{ t('about.whatWeDo.description') }}
      </p>
      <List>
        <ListItem>{{ t('about.whatWeDo.featherCleaning') }}</ListItem>
        <ListItem>{{ t('about.whatWeDo.manufacturing') }}</ListItem>
        <ListItem>{{ t('about.whatWeDo.renovation') }}</ListItem>
        <ListItem>{{ t('about.whatWeDo.fillReplacement') }}</ListItem>
      </List>
      <div class="mt-4 p-3 bg-accent/10 border-l-4 border-accent rounded">
        <p class="text-accent-700 font-medium">{{ t('about.whatWeDo.specialNote') }}</p>
      </div>
    </AboutCard>
    <AboutCard
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 200)"
      :title="t('about.values.title')"
      class="leading-relaxed"
    >
      <p class="text-muted-foreground mb-4">
        {{ t('about.values.description') }}
      </p>
      <List>
        <ListItem>{{ t('about.values.quality') }}</ListItem>
        <ListItem>{{ t('about.values.experience') }}</ListItem>
        <ListItem>{{ t('about.values.reliability') }}</ListItem>
        <ListItem>{{ t('about.values.pricing') }}</ListItem>
        <ListItem>{{ t('about.values.individual') }}</ListItem>
        <ListItem>{{ t('about.values.hygiene') }}</ListItem>
      </List>
    </AboutCard>
    <AboutCard
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 300)"
      :title="t('about.company.title')"
      class="leading-relaxed"
    >
      <p class="text-muted-foreground mb-4">
        {{ t('about.company.description') }}
      </p>
      <List>
        <ListItem>{{ t('about.company.phone') }}: {{ config.company.phone }}</ListItem>
        <ListItem>{{ t('about.company.phone2') }}: {{ config.company.phone2 }}</ListItem>
        <ListItem>{{ t('about.company.address') }}: {{ config.company.address }}</ListItem>
        <ListItem>{{ t('about.company.hours') }}: {{ config.company.hours.weekdays }}</ListItem>
        <ListItem>{{ config.company.hours.saturday }}</ListItem>
        <ListItem>{{ t('about.company.coverage') }}</ListItem>
      </List>
    </AboutCard>
  </BaseSection>
</template>
