<template>
  <div>
    <nav class="navbar is-fixed-top" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item brand" href="/"><img src="/img/logo.svg" class="coucherslogotop" /> <span class="couchersorgtop">Couchers.org</span></a>

        <a role="button" class="navbar-burger burger" v-bind:class="{ 'is-active': burger_active }" v-on:click="toggle_burger" aria-label="menu" aria-expanded="false" data-target="couchers-navbar">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div id="couchers-navbar" class="navbar-menu" v-bind:class="{ 'is-active': burger_active }">
        <div class="navbar-start">
          <div class="navbar-item is-hidden-desktop">
            <div class="buttons">
              <a class="button is-primary" href="https://app.couchers.org/signup">
                Create an account
              </a>
              <a class="button is-primary is-outlined" href="https://app.couchers.org/login">
                Log in
              </a>
              <a class="button navbar-github is-hidden-desktop" href="https://github.com/couchers-org/couchers">
                <span class="icon is-large"><i class="mdi mdi-github mdi-36px" aria-label="Couchers.org GitHub"></i></span>
              </a>
            </div>
          </div>

          <a class="navbar-item" href="/blog/">
            Blog
          </a>

          <div class="navbar-item has-dropdown is-hoverable">
            <a href="/plan/" class="navbar-link">
              Our Plan
            </a>

            <div class="navbar-dropdown">
              <a href="/plan/profit-and-incentives/" class="navbar-item">
                Non-Profit Structure
              </a>
              <a href="/plan/communities-and-trust/" class="navbar-item">
                Community-First Framework
              </a>
              <a href="/plan/creeps-and-freeloaders/" class="navbar-item">
                Member Accountability
              </a>
              <a href="/plan/reviews/" class="navbar-item">
                Improved Review System
              </a>
              <a href="/plan/host-matching/" class="navbar-item">
                Better Host Finding
              </a>
              <a href="/plan/the-build/" class="navbar-item">
                Building it Right
              </a>
            </div>
          </div>

          <div class="navbar-item has-dropdown is-hoverable">
            <a href="/issues/" class="navbar-link">
              Couchsurfing&#8482; Issues
            </a>

            <div class="navbar-dropdown">
              <a href="/issues/profit-and-incentives/" class="navbar-item">
                Profit and Incentives
              </a>
              <a href="/issues/communities-and-trust/" class="navbar-item">
                Neglected Communities
              </a>
              <a href="/issues/creeps-and-freeloaders/" class="navbar-item">
                Safety and Freeloaders
              </a>
              <a href="/issues/reviews/" class="navbar-item">
                The Reference System
              </a>
              <a href="/issues/host-matching/" class="navbar-item">
                The Super-Host Effect
              </a>
              <a href="/issues/the-build/" class="navbar-item">
                The Bugs and App Issues
              </a>
            </div>
          </div>

          <a class="navbar-item" href="/faq/">
            FAQ
          </a>

          <a class="navbar-item" href="/team/">
            The Team
          </a>
        </div>

        <div class="navbar-end">
          <a class="navbar-item" href="https://community.couchers.org/">
            Forum
          </a>

          <div class="is-hidden-touch navbar-item">
            <div class="buttons">
              <a class="button is-primary" href="https://app.couchers.org/signup">
                Create an account
              </a>
            </div>
          </div>

          <div class="is-hidden-touch navbar-item">
            <div class="buttons">
              <a class="button is-primary is-outlined" href="https://app.couchers.org/login">
                Log in
              </a>
            </div>
          </div>

          <a class="is-hidden-touch navbar-item navbar-github" href="https://github.com/couchers-org/couchers">
            <span class="icon is-large"><i class="mdi mdi-github mdi-36px" aria-label="Couchers.org GitHub"></i></span>
          </a>

          <span class="is-hidden-desktop bottom-spacing">&nbsp;</span>
        </div>
      </div>
    </nav>
    <Nuxt />
    <footer class="footer">
      <div class="content has-text-centered">
        <p>
          <a href="/blog/">The Blog</a> | <a href="/foundation/">Couchers.org Foundation</a> | <a href="/handbook/">Handbook</a> | <a href="/volunteer/">Volunteer</a> | <a href="/donate/">Donate</a> | <a href="/handbook/">Help</a>
        </p>
      </div>
      <div class="content has-text-centered">
        <p>
          Built with
          <span class="icon-text">
            <span class="icon is-small"><i class="mdi mdi-heart" aria-label="love"></i></span>
          </span>
          by <a href="/team/">the <b>Couchers.org team</b></a>.
        </p>
        <p>It's like Couchsurfing&#8482;, but better.</p>
        <p><img src="/img/logo.svg" class="coucherslogobottom" /></p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      burger_active: false
    }
  },
  methods: {
    toggle_burger: function () {
      this.burger_active = !this.burger_active
    }
  },
  head () {
    const description = "The new alternative to Couchsurfing™. Free forever. Non-profit. Community-focused. Well built."
    return {
      title: "Home",
      titleTemplate: '%s | Couchers.org',
      meta: [
        {
          property: 'og:title',
          template: chunk => (chunk ? chunk + ' | ' : '') + 'Couchers.org',
          hid: 'og:title'
        },

        {
          property: 'twitter:title',
          template: chunk => (chunk ? chunk + ' | ' : '') + 'Couchers.org',
          hid: 'twitter:title'
        },

        { hid: 'description', name: 'description', content: description },
        { hid: 'og:description', property: 'og:description', content: description },
        { hid: 'twitter:description', name: 'twitter:description', content: description },

        { hid: 'og:image', property: 'og:image', content: 'https://couchers.org/img/share.jpg' },
        { hid: 'twitter:image', name: 'twitter:image', content: 'https://couchers.org/img/share.jpg' },

        // { hid: 'og:url', property: 'og:url', content: 'https://couchers.org' },
        { hid: 'og:type', property: 'og:type', content: 'website' },
        { hid: 'twitter:card', name: 'twitter:card', content: 'summary_large_image' }
      ]
    }
  }
}
</script>

<style>
@import url("node_modules/@mdi/font/css/materialdesignicons.css");

.navbar {
  box-shadow: 0px 2px 4px -1px rgba(0,0,0,0.2),0px 4px 5px 0px rgba(0,0,0,0.14),0px 1px 10px 0px rgba(0,0,0,0.12);
}

.navbar-item, .navbar-link {
  color: rgba(0, 0, 0, 0.54);
  font-size: 0.875rem;
  font-weight: 700;
}

.buttons > .button {
  font-size: 0.875rem !important;
  font-weight: 700 !important;
}

.couchers-button {
  font-weight: 700 !important;
}

.navbar-github {
  color: #313539;
  border: none !important;
}

.bottom-spacing {
  display: block;
  width: 1px;
  height: 20vh;
}

.brand {
  font-weight: 700;
}

.coucherslogotop {
  max-height: 3.125rem !important;
  width: 3.125rem;
  height: 3.125rem;
  vertical-align: middle;
}

.couchersorgtop {
  font-family: 'Mansalva', sans-serif;
  font-weight: 400 !important;
  font-size: 2rem;
  margin-inline-start: 1.5;
  color: #e47701;
  vertical-align: middle;
  white-space: nowrap;
}

.coucherslogobottom {
  width: 6rem;
  height: 6rem;
}
</style>
