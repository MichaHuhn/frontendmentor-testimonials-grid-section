<script setup>
defineProps(['image', 'name', 'heading', 'quote']);
</script>

<template>
  <article>
    <header>
      <img :src="image.src" :alt="image.alt" class="photo">
      <div>
        <div class="name">{{ name }}</div>
        <div class="verified-graduate">Verified Graduate</div>
      </div>
    </header>
    
    <h2 class="heading">{{ heading }}</h2>
    
    <blockquote>{{ quote }}</blockquote>
  </article>
</template>

<style scoped lang="scss">
@import '@/assets/styles/base/media-queries';

article {
  --color-translucent: hsl(from var(--color) h s l / 0.5);
  
  height: 100%;
  padding: 1.625rem 2rem 2rem;
  color: var(--color);
  background-color: var(--background-color);
  border-radius: 8px;
  box-shadow: 40px 60px 50px -47px hsl(217deg 19% 35% / 24.74%);
  
  header {
    margin-bottom: calc(19 / 16 * 1rem);
    display: flex;
    align-items: center;
    gap: calc(17 / 16 * 1rem);
    
    .photo {
      --size: 1.75rem;
      
      width: var(--size);
      height: var(--size);
      border-radius: 100vmax;
      outline: 2px solid var(--color-photo-outline);
    }
    
    .name {
      line-height: 1;
      transform: translateY(-2px); /* optical alignment */
    }
    
    .verified-graduate {
      color: var(--color-translucent);
      font-size: calc(11 / 16 * 1rem);
      line-height: 1;
      transform: translateY(2px); /* optical alignment */
    }
  }
  
  .heading {
    font-size: 1.25rem;
    font-weight: 600;
    line-height: 1.2;
  }
  
  blockquote {
    margin-block-start: 1rem;
    color: var(--color-translucent);
    line-height: calc(18 / 13);
    
    &::before {
      content: '" '
    }
    
    &::after {
      content: ' "'
    }
  }
}
</style>
