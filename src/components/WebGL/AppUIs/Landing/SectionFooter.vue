<template>
  <footer class="section-footer relative pt-24 pb-6">
    <div
      class="bottom-auto top-0 left-0 right-0 w-full absolute pointer-events-none overflow-hidden -mt-20"
      style="height: 80px; transform: translateZ(0px);"
    >
      <svg
        class="absolute bottom-0 overflow-hidden"
        xmlns="http://www.w3.org/2000/svg"
        preserveAspectRatio="none"
        version="1.1"
        viewBox="0 0 2560 100"
        x="0"
        y="0"
      >
        <polygon
          fill="#08080d"
          points="2560 0 2560 100 0 100"
        ></polygon>
      </svg>
    </div>
    <div class="container mx-auto px-4">
      <div class="flex flex-wrap">
        <div class="w-full lg:w-6/12 px-4">
          <h4 class="text-3xl font-semibold" style="color: var(--cosmos-text); font-family: var(--font-display); font-weight: 700;">Let's keep in touch!</h4>
          <h5 class="text-lg mt-0 mb-2" style="color: var(--cosmos-text-muted);">
            Find Lok Lok on any of these platforms, he usually hangout on Instagram.
          </h5>
          <div class="mt-6 flex flex-wrap gap-2">
            <a
              class="social-icon social-icon-twitter"
              target="_blank" href="https://twitter.com/wonglok831"
            >
              <i class="flex fab fa-twitter"></i></a>
            <a
              class="social-icon social-icon-facebook"
              target="_blank" href="https://facebook.com/thankyoujesuswithloklok"
            >
              <i class="flex fab fa-facebook-square"></i></a>
            <a
              class="social-icon social-icon-instagram"
              target="_blank" href="https://instagram.com/effectnode"
            >
              <i class="flex fab fa-instagram"></i></a>
            <a
              class="social-icon social-icon-github"
              target="_blank" href="https://github.com/wonglok"
            >
              <i class="flex fab fa-github"></i>
            </a>
            <a
              class="social-icon social-icon-linkedin"
              target="_blank" href="https://www.linkedin.com/in/wonglok831/"
            >
              <i class="flex fab fa-linkedin"></i>
            </a>
          </div>
        </div>
        <div class="w-full lg:w-6/12 px-4 pt-8 md:pt-0">
          <div class="flex flex-wrap items-top mb-6">
            <div class="w-full lg:w-4/12 px-4 ml-auto">
              <span
                class="block uppercase text-sm font-semibold mb-2"
                style="color: var(--cosmos-text-dim); letter-spacing: 0.1em;"
                >Lok's Links</span>
              <ul class="list-unstyled">
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="http://o3d-gen3.vercel.app/"
                    >O3D-GEN3</a>
                </li>
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://effectnode.com"
                    >Effect Node</a>
                </li>
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://www.iadas.net/membership/bio/lok-wong/7842"
                    >Webbys / IADAS</a>
                </li>
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://creativecodelab.com"
                    >Creative Code Lab</a>
                </li>
              </ul>
            </div>
            <div class="w-full lg:w-4/12 px-4 mt-12 md:mt-0">
              <span
                class="block uppercase text-sm font-semibold mb-2"
                style="color: var(--cosmos-text-dim); letter-spacing: 0.1em;"
                >Other Links</span>
              <ul class="list-unstyled">
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://github.com/wonglok/loklok-academy/blob/master/LICENSE.md"
                    >MIT License</a>
                </li>
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://www.linkedin.com/in/wonglok831/"
                    >Linked In</a>
                </li>
                <li>
                  <a
                    class="footer-link font-semibold block pb-2 text-sm"
                    target="_blank" href="https://instagram.com/effectnode"
                    >Contact Lok Lok</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <hr class="footer-divider my-6" />

      <div
        class="flex flex-wrap items-center md:justify-between justify-center"
      >
        <div class="w-full md:w-4/12 px-4 mx-auto text-center">
          <div class="text-sm font-semibold py-1" style="color: var(--cosmos-text-dim);">
            Copyright &copy; 2020
            <a
              target="_blank" href="https://www.wonglok.com"
              class="footer-link"
              >Wong Lok</a
            >.
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {

}
</script>

<style>
.section-footer {
  background-color: #08080d;
}

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(255, 255, 255, 0.06);
  font-size: 14px;
  outline: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
}
.social-icon:hover {
  transform: translateY(-2px);
}
.social-icon-twitter {
  color: #1da1f2;
}
.social-icon-twitter:hover {
  box-shadow: 0 0 16px rgba(29, 161, 242, 0.25);
  border-color: rgba(29, 161, 242, 0.3);
}
.social-icon-facebook {
  color: #4267b2;
}
.social-icon-facebook:hover {
  box-shadow: 0 0 16px rgba(66, 103, 178, 0.25);
  border-color: rgba(66, 103, 178, 0.3);
}
.social-icon-instagram {
  color: #e1306c;
}
.social-icon-instagram:hover {
  box-shadow: 0 0 16px rgba(225, 48, 108, 0.25);
  border-color: rgba(225, 48, 108, 0.3);
}
.social-icon-github {
  color: #c9d1d9;
}
.social-icon-github:hover {
  box-shadow: 0 0 16px rgba(201, 209, 217, 0.15);
  border-color: rgba(201, 209, 217, 0.2);
}
.social-icon-linkedin {
  color: #0a66c2;
}
.social-icon-linkedin:hover {
  box-shadow: 0 0 16px rgba(10, 102, 194, 0.25);
  border-color: rgba(10, 102, 194, 0.3);
}

.footer-link {
  color: var(--cosmos-text-muted);
  transition: color 0.2s ease;
  text-decoration: none;
}
.footer-link:hover {
  color: var(--cosmos-text);
}

.footer-divider {
  border: none;
  border-top: 1px solid rgba(255, 255, 255, 0.06);
}
</style>
