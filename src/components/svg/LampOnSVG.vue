<template>
  <svg width="40" height="69" viewBox="0 0 40 50" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path
      d="M19.584 56.585a7.311 7.311 0 01-7.311-7.312v-5.758h14.623v5.758a7.312 7.312 0 01-7.312 7.312z"
      fill="#FEC165"
      class="bulb"
    />
    <path
      d="M19.584 35.871a1.01 1.01 0 01-1.01-1.01V1.01a1.01 1.01 0 112.021 0v33.85a1.01 1.01 0 01-1.01 1.01z"
      fill="#465A61"
      class="cable"
    />
    <path
      d="M24.418 30.31h-9.667v-9.733a2.482 2.482 0 012.482-2.482h4.703a2.482 2.482 0 012.482 2.482v9.732z"
      fill="#596C76"
      class="base"
    />
    <path
      d="M24.418 23.99v.212l-7.502-.632C7.363 24.872 0 33.062 0 42.973v5.73c0 .744.603 1.347 1.348 1.347H37.82c.744 0 1.348-.603 1.348-1.348v-5.73c0-9.147-6.272-16.83-14.75-18.982z"
      fill="#7A8C98"
      class="holder"
    />
    <path
      d="M19.584 69a1.01 1.01 0 01-1.01-1.01v-6.071a1.01 1.01 0 112.021 0v6.07A1.01 1.01 0 0119.585 69z"
      fill="#FDB441"
      class="line line-1"
    />
    <path
      d="M34.771 63.194c-.259 0-.517-.099-.715-.296l-4.288-4.293a1.01 1.01 0 011.43-1.428l4.288 4.292a1.011 1.011 0 01-.715 1.725z"
      fill="#FDB441"
      class="line line-2"
    />
    <path
      d="M4.398 63.194a1.01 1.01 0 01-.715-1.725l4.288-4.293a1.01 1.01 0 011.43 1.43l-4.288 4.292a1.008 1.008 0 01-.715.296z"
      fill="#FDB441"
      class="line line-3"
    />
    <path
      d="M19.584 23.389c-.907 0-1.8.063-2.674.182 9.551 1.304 16.91 9.493 16.91 19.402v5.73c0 .744-.603 1.347-1.347 1.347h5.348c.744 0 1.348-.603 1.348-1.348v-5.73c0-10.815-8.768-19.583-19.585-19.583z"
      fill="#596C76"
      class="shadow"
    />
  </svg>
</template>

<style scoped>
.animated path {
  transition: all 300ms ease-in-out;
}

.animated .line {
  --start: 300ms;
  --delay-1: var(--start);
  --delay-2: calc(var(--delay-1) / 2);
  --delay-3: calc(var(--delay-2) / 2);
}

.animated.on {
  filter: drop-shadow(0 20px 10px rgb(254 193 101 / 30%));

  .line {
    opacity: 0;
    animation: turn-on-lines 300ms ease-in-out forwards;
  }

  .line-1 {
    animation-delay: var(--delay-2);
  }

  .line-2 {
    animation-delay: var(--delay-3);
  }

  .line-3 {
    animation-delay: var(--delay-1);
  }
}

.animated.off {
  .line {
    animation: turn-off-lines 300ms ease-in-out forwards;
  }

  .line-1 {
    animation-delay: var(--delay-2);
  }

  .line-2 {
    animation-delay: var(--delay-1);
  }

  .line-3 {
    animation-delay: var(--delay-3);
  }

  .holder {
    fill: var(--color-gray-800);
  }

  .shadow,
  .cable,
  .base {
    fill: var(--color-default-black);
  }

  .bulb {
    animation: turn-off-bulb 800ms ease-in-out forwards;
  }
}

@keyframes turn-off-lines {
  0% {
    opacity: 1;
  }

  50% {
    opacity: 0.5;
  }

  100% {
    opacity: 0;
  }
}

@keyframes turn-on-lines {
  0% {
    opacity: 0;
  }

  50% {
    opacity: 0.5;
  }

  100% {
    opacity: 1;
  }
}

@keyframes turn-off-bulb {
  from {
    fill: hsl(36deg 99% 70%);
  }

  to {
    fill: hsl(0deg 0% 88%);
  }
}
</style>
