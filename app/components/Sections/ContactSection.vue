<script setup lang="ts">
import { Briefcase, Building, Mail, MapPin, Phone, Rocket, ShieldCheck, Shirt, Droplets, Scissors } from 'lucide-vue-next'
import { useI18n } from '#imports'
import { config } from '@/config'
import { useAnimationConfig } from '@/composables/useAnimationConfig'
import BaseSection from './BaseSection.vue'
import CardComponent from '../Cards/ContactCard.vue'
import { HoverLink } from '../ui/hoverLink'

const { t } = useI18n()
const { slideUp, delayed } = useAnimationConfig()
</script>

<template>
  <BaseSection id="contact" :title="t('contact.title')">
    <CardComponent
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 100)"
    >
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <Briefcase class="size-6" />
        <div class="font-semibold">
          {{ config.company.name }}
        </div>
      </div>
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <MapPin class="size-6" />
        <div>
          <span class="font-semibold">{{ t('about.company.address') }}:</span>
          {{ config.company.address }}
        </div>
      </div>
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <ShieldCheck class="size-6" />
        <div>
          <span class="font-semibold">{{ t('about.company.hours') }}:</span>
          {{ config.company.hours.weekdays }}
        </div>
      </div>
    </CardComponent>

    <CardComponent
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 200)"
    >
      <HoverLink
        :href="`tel:${config.company.phone.replaceAll(' ', '')}`"
        aria-label="Phone"
      >
        <Phone class="size-6" />
        <span>{{ config.company.phone }}</span>
      </HoverLink>
      <HoverLink
        :href="`tel:${config.company.phone2.replaceAll(' ', '')}`"
        aria-label="Phone 2"
      >
        <Phone class="size-6" />
        <span>{{ config.company.phone2 }}</span>
      </HoverLink>
      <HoverLink
        :href="config.company.addressUrl"
        target="_blank"
        aria-label="Address"
      >
        <MapPin class="size-6" />
        <span>{{ config.company.address }}</span>
      </HoverLink>
    </CardComponent>

    <CardComponent
      v-motion
      :initial="slideUp.initial"
      :visible-once="delayed(slideUp.visibleOnce, 300)"
    >
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <Shirt class="size-6" />
        <div>
          <span class="font-semibold">{{ t('contact.services') }}</span>
        </div>
      </div>
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <Droplets class="size-6" />
        <div>
          <span class="font-semibold">{{ t('contact.cleaning') }}</span>
        </div>
      </div>
      <div class="flex gap-4 items-center px-4 py-3 rounded-full">
        <Scissors class="size-6" />
        <div>
          <span class="font-semibold">{{ t('contact.sewing') }}</span>
        </div>
      </div>
    </CardComponent>
  </BaseSection>
</template>
