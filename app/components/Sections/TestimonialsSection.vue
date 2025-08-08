<script setup lang="ts">
import BaseSection from '@/components/Sections/BaseSection.vue';
import TestimonialCard from '@/components/Cards/TestimonialCard.vue';

const { t } = useI18n();

const testimonials = [
  {
    author: "Jan Madeyski",
    date: "2023",
    location: "Warszawa",
    content: "Jestem bardzo zadowolony ze współpracy"
  }
]
</script>

<template>
  <BaseSection :title="t('testimonials.title')">
    <TestimonialCard
      v-for="testimonial in testimonials"
      :key="`${testimonial.author}-${testimonial.date}`"
      :author="testimonial.author"
      :date="testimonial.date"
      :location="testimonial.location"
      :content="testimonial.content"
    />
  </BaseSection>
</template>
