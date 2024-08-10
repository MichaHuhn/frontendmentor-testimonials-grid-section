<script setup>
import TestimonialCard from '@/components/TestimonialCard.vue';
import PhotoDaniel from '@/assets/images/daniel.jpg';
import PhotoJonathan from '@/assets/images/jonathan.jpg';
import PhotoJeanette from '@/assets/images/jeanette.jpg';
import PhotoPatrick from '@/assets/images/patrick.jpg';
import PhotoKira from '@/assets/images/kira.jpg';
</script>

<template>
  <main>
    <ul class="testimonial-list max-width-wrapper">
      <li class="testimonial-list-item">
        <TestimonialCard
          class="testimonial-card"
          :image="{ src: PhotoDaniel, alt: 'Testimonial photo of Daniel Clifford' }"
          name="Daniel Clifford"
          heading="I received a job offer mid-course, and the subjects I learned were current, if not more so, in the company I joined. I honestly feel I got every penny’s worth."
          quote="I was an EMT for many years before I joined the bootcamp. I’ve been looking to make a transition and have heard some people who had an amazing experience here. I signed up for the free intro course and found it incredibly fun! I enrolled shortly thereafter. The next 12 weeks was the best - and most grueling - time of my life. Since completing the course, I’ve successfully switched careers, working as a Software Engineer at a VR startup."
        />
      </li>
      <li class="testimonial-list-item">
        <TestimonialCard
          class="testimonial-card"
          :image="{ src: PhotoJonathan, alt: 'Testimonial photo of Jonathan Walters' }"
          name="Jonathan Walters"
          heading="The team was very supportive and kept me motivated"
          quote="I started as a total newbie with virtually no coding skills. I now work as a mobile engineer for a big company. This was one of the best investments I’ve made in myself."
        />
      </li>
      <li class="testimonial-list-item">
        <TestimonialCard
          class="testimonial-card"
          :image="{ src: PhotoJeanette, alt: 'Testimonial photo of Jeanette Harmon' }"
          name="Jeanette Harmon"
          heading="An overall wonderful and rewarding experience"
          quote="Thank you for the wonderful experience! I now have a job I really enjoy, and make a good living while doing something I love."
        />
      </li>
      <li class="testimonial-list-item">
        <TestimonialCard
          class="testimonial-card"
          :image="{ src: PhotoPatrick, alt: 'Testimonial photo of Patrick Abrams' }"
          name="Patrick Abrams"
          heading="Awesome teaching support from TAs who did the bootcamp themselves. Getting guidance from them and learning from their experiences was easy."
          quote="The staff seem genuinely concerned about my progress which I find really refreshing. The program gave me the confidence necessary to be able to go out in the world and present myself as a capable junior developer. The standard is above the rest. You will get the personal attention you need from an incredible community of smart and amazing people."
        />
      </li>
      <li class="testimonial-list-item">
        <TestimonialCard
          class="testimonial-card"
          :image="{ src: PhotoKira, alt: 'Testimonial photo of Kira Whittle' }"
          name="Kira Whittle"
          heading="Such a life-changing experience. Highly recommended!"
          quote="Before joining the bootcamp, I’ve never written a line of code. I needed some structure from professionals who can help me learn programming step by step. I was encouraged to enroll by a former student of theirs who can only say wonderful things about the program. The entire curriculum and staff did not disappoint. They were very hands-on and I never had to wait long for assistance. The agile team project, in particular, was outstanding. It took my learning to the next level in a way that no tutorial could ever have. In fact, I’ve often referred to it during interviews as an example of my development experience. It certainly helped me land a job as a full-stack developer after receiving multiple offers. 100% recommend!"
        />
      </li>
    </ul>
  </main>
</template>

<style scoped lang="scss">
@import '@/assets/styles/base/media-queries';

main {
  min-height: 100vh; /* fallback */
  min-height: 100dvh;
  padding: calc(71 / 16 * 1rem) 1.5rem;
  display: grid;
  place-content: center;
  
  .testimonial-list {
    padding: 0;
    list-style: none;
    display: grid;
    gap: 1.5rem;
    grid-auto-columns: 1fr;
    grid-template-areas:
      'one'
      'two'
      'three'
      'four'
      'five';
    
    @media #{$laptop-and-bigger} {
      grid-template-areas:
        'one one two five'
        'three four four five';
      gap: 1.5rem 1.875rem;
    }
    
    .testimonial-list-item {
      &:nth-of-type(1) {
        grid-area: one;
        
        .testimonial-card {
          --color: var(--color-white);
          --background-color: var(--color-moderate-violet);
          
          background-image: url('@/assets/images/background-pattern-quotation.svg');
          background-position: top right 1.5rem;
          background-repeat: no-repeat;
          
          @media #{$laptop-and-bigger} {
            background-position: top right 5rem;
          }
        }
      }
      
      &:nth-of-type(2) {
        grid-area: two;
        
        .testimonial-card {
          --color: var(--color-white);
          --background-color: var(--color-very-dark-grayish-blue);
        }
      }
      
      &:nth-of-type(3) {
        grid-area: three;
        
        .testimonial-card {
          --color: var(--color-very-dark-grayish-blue);
          --background-color: var(--color-white);
        }
      }
      
      &:nth-of-type(4) {
        grid-area: four;
        
        .testimonial-card {
          --color: var(--color-light-grayish-blue);
          --background-color: var(--color-very-dark-blackish-blue);
        }
      }
      
      &:nth-of-type(5) {
        grid-area: five;
        
        .testimonial-card {
          --color: var(--color-very-dark-grayish-blue);
          --background-color: var(--color-white);
        }
      }
    }
  }
}

.max-width-wrapper {
  max-width: calc(1110 / 16 * 1rem);
  margin-inline: auto;
}
</style>
