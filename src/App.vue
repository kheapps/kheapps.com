<template>
  <div class="landing">
    <div class="landing-text">
      <span v-for="(c, i) in 'KHEAPPS'" :key="i"> {{ c }} </span>
    </div>
    <p>Work in progress</p>
  </div>
</template>

<style lang="scss">
@import "./assets/base.scss";

.landing {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .landing-text {
    height: 200px;
    width: $landing-text-size-lg * 7;
    font-size: $landing-text-size-lg;
  }

  span {
    position: absolute;
    animation: jump 3s ease infinite;
  }

  @for $i from 1 to 8 {
    span:nth-child(#{$i}) {
      animation-delay: $i * 150ms;
      left: ($i - 1) * $landing-text-size-lg;
    }
  }

  p {
    font-size: 3rem;
  }

  @media only screen and (max-width: $xs) {
    .landing-text {
      height: 70px;
      width: $landing-text-size-xs * 7;
      font-size: $landing-text-size-xs;
    }
    @for $i from 1 to 8 {
      span:nth-child(#{$i}) {
        left: ($i - 1) * $landing-text-size-xs;
      }
    }
    p {
      font-size: 1.5rem;
    }
  }

  @media only screen and (min-width: $xs) and (max-width: $sm) {
    .landing-text {
      height: 150px;
      width: $landing-text-size-sm * 7;
      font-size: $landing-text-size-sm;
    }
    @for $i from 1 to 8 {
      span:nth-child(#{$i}) {
        left: ($i - 1) * $landing-text-size-sm;
      }
    }
    p {
      font-size: 2rem;
    }
  }
}

@keyframes jump {
  0% {
    transform: translateY(0);
  }

  20% {
    transform: translateY(-30px);
  }

  40% {
    transform: translateY(0);
  }

  100% {
    transform: translateY(0);
  }
}
</style>
