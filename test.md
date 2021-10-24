<div class="brasil" data-text="COMING SOON">COMING SOON</div>

<style>
  body {
  background: #000;
  display: flex;
  align-items: center;
  height: 100vh;
  justify-content: center;
}

.brasil {
  font-family: arial;
  position: relative;
   color: #fff;
  text-align: center;
  font-size: 7rem;
  max-width: 1200px;
  margin: 0 auto;
}
.brasil::before,
.brasil::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.brasil::before {
  left: 2px;
    clip: rect(79px, 1200px, 86px, 0);
  text-shadow: -1px 0 red;
  background: #000;
  animation: brasil-anim-2 1s infinite linear alternate-reverse;
}

.brasil::after {
  /* variation */
  left: -2px;
  clip: rect(79px, 1200px, 86px, 0);
  text-shadow: -1px 0 blue;
  background: #000;
  animation: brasil-anim-1 1s infinite linear alternate-reverse;
   animation-delay: -1s;
}

@keyframes brasil-anim-1 {
  0% {
    clip: rect(20px, 1200px, 76px, 0);
  }
  20% {
    clip: rect(19px, 1200px, 16px, 0);
  }
  40% {
    clip: rect(16px, 1200px, 3px, 0);
  }
  60% {
    clip: rect(62px, 1200px, 78px, 0);
  }
  80% {
    clip: rect(25px, 1200px, 13px, 0);
  }
  100% {
    clip: rect(53px, 1200px, 86px, 0);
  }
}

@keyframes brasil-anim-2 {
  0% {
    clip: rect(79px, 1200px, 86px, 0);
  }
  
  20% {
    clip: rect(20px, 1200px, 30px, 0)
  }
  
  40% {
    clip: rect(25px, 1200px, 5px, 0)
  }
  
  60% {
    clip: rect(65px, 1200px, 85px, 0)
  }
  
  80% {
    clip: rect(120px, 1200px, 145px, 0)
  }
  
  100% {
    clip: rect(95px, 1200px, 75px, 0)
  }
}
</style>
   raw • new • about
