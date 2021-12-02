<template>
  <div class="home">
    <div class="lines"></div>
    <p></p>
    <p></p>

    <h2>Happy Birthday!</h2>

    <p></p>
    <p></p>
    <div id="emitter">
      <button class="button-49" v-on:click="birthday()">BIRTHDAY()</button>
    </div>
    <!-- <p>Times Amanda has been wished a happy birthday today: {{ this.clicks }}</p> -->
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>

    <div class="perspective-text">
      <div class="perspective-line">
        <p></p>
        <p>Times Amanda has</p>
      </div>
      <div class="perspective-line">
        <p>Times Amanda has</p>
        <p>been wished a</p>
      </div>
      <div class="perspective-line">
        <p>been wished a</p>
        <p>happy birthday today:</p>
      </div>
      <div class="perspective-line">
        <p>happy birthday today:</p>
        <p>{{ this.clicks }}</p>
      </div>
      <div class="perspective-line">
        <p>{{ this.clicks }}</p>
        <p></p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Mr+Dafoe&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Exo:wght@900&display=swap");

.lines {
  color: #59c1fe;
  position: fixed;
  width: 100vw;
  height: 4em;
  background: linear-gradient(rgba(color, 0.2) 20%, color 40%, color 60%, rgba(color, 0.2) 80%);
  background-size: 1px 0.5em;
  box-shadow: 0 0 1em rgba(color, 0.4);
  transform: translateY(-1em);
  left: 0;
}

h2 {
  font-family: "Mr Dafoe";
  margin: 0;
  font-size: 5.5em;
  margin-top: -0.6em;
  color: white;
  text-shadow: 0 0 0.05em #fff, 0 0 0.2em #fe05e1, 0 0 0.3em #fe05e1;
  transform: rotate(-7deg);
}

.home {
  text-align: center;
  /* background-image: url("https://cdn.mos.cms.futurecdn.net/sticNbxxFvVjohQGfoDVfk-1200-80.jpg"); */
}

.button-49,
.button-49:after {
  width: 150px;
  height: 76px;
  line-height: 78px;
  font-size: 20px;
  font-family: "Bebas Neue", sans-serif;
  background: linear-gradient(45deg, transparent 5%, #ff013c 5%);
  border: 0;
  color: #fff;
  letter-spacing: 3px;
  box-shadow: 6px 0px 0px #00e6f6;
  outline: transparent;
  position: relative;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-49:after {
  --slice-0: inset(50% 50% 50% 50%);
  --slice-1: inset(80% -6px 0 0);
  --slice-2: inset(50% -6px 30% 0);
  --slice-3: inset(10% -6px 85% 0);
  --slice-4: inset(40% -6px 43% 0);
  --slice-5: inset(80% -6px 5% 0);

  content: "CELEBRATE";
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, transparent 3%, #00e6f6 3%, #00e6f6 5%, #ff013c 5%);
  text-shadow: -3px -3px 0px #f8f005, 3px 3px 0px #00e6f6;
  clip-path: var(--slice-0);
}

.button-49:hover:after {
  animation: 1s glitch;
  animation-timing-function: steps(2, end);
}

@keyframes glitch {
  0% {
    clip-path: var(--slice-1);
    transform: translate(-20px, -10px);
  }
  10% {
    clip-path: var(--slice-3);
    transform: translate(10px, 10px);
  }
  20% {
    clip-path: var(--slice-1);
    transform: translate(-10px, 10px);
  }
  30% {
    clip-path: var(--slice-3);
    transform: translate(0px, 5px);
  }
  40% {
    clip-path: var(--slice-2);
    transform: translate(-5px, 0px);
  }
  50% {
    clip-path: var(--slice-3);
    transform: translate(5px, 0px);
  }
  60% {
    clip-path: var(--slice-4);
    transform: translate(5px, 10px);
  }
  70% {
    clip-path: var(--slice-2);
    transform: translate(-10px, 10px);
  }
  80% {
    clip-path: var(--slice-5);
    transform: translate(20px, -10px);
  }
  90% {
    clip-path: var(--slice-1);
    transform: translate(-10px, 0px);
  }
  100% {
    clip-path: var(--slice-1);
    transform: translate(0);
  }
}

@media (min-width: 768px) {
  .button-49,
  .button-49:after {
    width: 200px;
    height: 86px;
    line-height: 88px;
  }
}

html {
  height: 100%;
}

body {
  background-image: url("https://cdn.mos.cms.futurecdn.net/sticNbxxFvVjohQGfoDVfk-1200-80.jpg");
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f1f1f1;
  overflow: hidden;
  margin-left: auto;
  margin-right: auto;
  margin-top: 250px;
}

.perspective-text {
  color: white;
  font-family: Arial;
  font-size: 58px;
  font-weight: 900;
  letter-spacing: -2px;
  text-transform: uppercase;
}

.perspective-line {
  height: 50px;
  overflow: hidden;
  position: relative;
}

p {
  margin: 0;
  height: 50px;
  line-height: 50px;
  transition: all 0.5s ease-in-out;
}

.perspective-line:nth-child(odd) {
  transform: skew(60deg, -30deg) scaleY(0.667);
}

.perspective-line:nth-child(even) {
  transform: skew(0deg, -30deg) scaleY(1.337);
}

.perspective-text:hover p {
  transform: translate(0, -50px);
}

.perspective-line:nth-child(1) {
  left: 29px;
}

.perspective-line:nth-child(2) {
  left: 58px;
  background: #f07e6e;
}

.perspective-line:nth-child(3) {
  left: 87px;
  background: #84cdfa;
}

.perspective-line:nth-child(4) {
  left: 116px;
  background: #5ad1cd;
}

.perspective-line:nth-child(5) {
  left: 145px;
}
</style>

<script>
import confetti from "canvas-confetti";
export default {
  data: function () {
    return {
      clicks: 0,
    };
  },
  methods: {
    birthday: function () {
      var count = 200;
      var defaults = {
        angle: 75,
        origin: { x: 0, y: 0.6 },
      };

      var defaultsTwo = {
        angle: 100,
        origin: { x: 1, y: 0.6 },
      };

      function fire(particleRatio, opts) {
        confetti(
          Object.assign({}, defaults, opts, {
            particleCount: Math.floor(count * particleRatio),
          })
        );
      }

      fire(0.25, {
        spread: 26,
        startVelocity: 55,
      });
      fire(0.2, {
        spread: 60,
      });
      fire(0.35, {
        spread: 100,
        decay: 0.91,
        scalar: 0.8,
      });
      fire(0.1, {
        spread: 120,
        startVelocity: 25,
        decay: 0.92,
        scalar: 1.2,
      });
      fire(0.1, {
        spread: 120,
        startVelocity: 45,
      });

      function fireTwo(particleRatio, opts) {
        confetti(
          Object.assign({}, defaultsTwo, opts, {
            particleCount: Math.floor(count * particleRatio),
          })
        );
      }

      fireTwo(0.25, {
        spread: 26,
        startVelocity: 55,
      });
      fireTwo(0.2, {
        spread: 60,
      });
      fireTwo(0.35, {
        spread: 100,
        decay: 0.91,
        scalar: 0.8,
      });
      fireTwo(0.1, {
        spread: 120,
        startVelocity: 25,
        decay: 0.92,
        scalar: 1.2,
      });
      fireTwo(0.1, {
        spread: 120,
        startVelocity: 45,
      });

      this.clicks += 1;
    },
  },
};
</script>
