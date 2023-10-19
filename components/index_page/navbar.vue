<template>

    <div>

        <Head>
            <Body :class="{'overflow-hidden': menuOpen}"></Body>
        </Head>

        <div class="nav absolute w-full top-0 left-0 py-10 overflow-y-scroll"
             :class="{'menuOpen fixed h-full pb-0 nav-overlay': menuOpen}">
            <div class="z-40">
                <div class="container flex justify-between">
                    <nuxt-link to="/" class="">
                        <nuxt-img class="logo" src="/images/logo.svg"/>
                    </nuxt-link>

                    <div class="flex items-center">
                        <nuxt-link to="https://docs.google.com/forms/d/e/1FAIpQLSdWGxJCVb_fKajIlBFxGXdWpRGjxHlSQ1sSw4LGIpW5kLHGBQ/viewform" class="underline mb-2 mr-12 hidden md:block"
                                   target="_blank">Salvadoran Satellite LoL
                        </nuxt-link>
                        <a v-on:click="menuOpen = !menuOpen" class="h-18 w-18 cursor-pointer">
                            <div class="m-auto" :class="menuOpen ? 'hidden' : 'visible'">
                                <span class="material-symbols-outlined text-5xl">drag_handle</span>
                            </div>

                            <div class="m-auto" :class="menuOpen ? 'visible' : 'hidden'">
                                <span class="material-symbols-outlined text-5xl">close</span>
                            </div>
                        </a>
                    </div>
                </div>
                <div class="w-full md:hidden flex justify-between">
                    <div class="mx-auto mt-5">
                        <nuxt-link to="https://talks.adoptingbitcoin.org" class="underline" target="_blank">Call for
                            participation
                        </nuxt-link>
                    </div>

                </div>
            </div>

            <div class="w-full h-full py-16" v-if="menuOpen">
                <div class="bg-clouds w-full top-0 left-0 h-fit absolute -z-20"></div>
                <div class="container">
                    <div class="flex flex-col menu-links text-right">
                        <nuxt-link to="/#venue" v-on:click="menuOpen = false">venue</nuxt-link>
                        <nuxt-link to="/#speakers" v-on:click="menuOpen = false">speakers</nuxt-link>
                        <nuxt-link to="/#ticket" v-on:click="menuOpen = false">ticket</nuxt-link>
                        <nuxt-link to="/#sponsors" v-on:click="menuOpen = false">sponsors</nuxt-link>
                        <nuxt-link to="/#partners" v-on:click="menuOpen = false">partners</nuxt-link>
                        <nuxt-link to="/#team" v-on:click="menuOpen = false">team</nuxt-link>

                        <nuxt-link to="https://talks.adoptingbitcoin.org/adopting-bitcoin-2023/schedule/" target="_blank">Schedule
                        </nuxt-link>
                        <nuxt-link to="https://docs.google.com/forms/d/e/1FAIpQLSdWGxJCVb_fKajIlBFxGXdWpRGjxHlSQ1sSw4LGIpW5kLHGBQ/viewform" target="_blank">Legends of Lightning
                        </nuxt-link>
                        <nuxt-link to="/faq">FAQ</nuxt-link>
                    </div>

                </div>

            </div>

        </div>


    </div>

</template>

<script>
export default {
    data() {
        return {
            menuOpen: false
        }
    },

    head() {
        return {
            bodyAttrs: {
                class: this.menuOpen ? 'overflow-hidden' : ''
            }
        }
    },
}
</script>

<style scoped lang="scss">
.nav {
  z-index: 9999;
}

.menuOpen {
  @apply fixed;
}

.logo {
  @apply z-10 h-full w-auto;
}

.nav-overlay {
  background-color: #252525;
  z-index: 9998;
}

.menu-links {

  a {
    z-index: 99999;
    @apply text-lg my-1 md:my-0 md:text-4xl hover:underline text-white;
  }
}
</style>
