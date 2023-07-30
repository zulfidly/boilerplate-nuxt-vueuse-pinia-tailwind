<template>
  <Notifier ref="exposeNotifierRef" />
  <div>
    <NuxtWelcome />
  </div>
</template>

<script setup>
const appStore = useMainStorePinia()
 const exposeNotifierRef = ref(null)
 function displayNotifier(text, duration) { exposeNotifierRef.value.showNotifier(text.toString(), duration)}

useHead({
    title: 'TabTitle',
    script: `if(window.matchMedia("(prefers-color-scheme:dark)").matches) document.querySelector('html').classList.add('dark')`,
    htmlAttrs:{ lang:'en', class: {  } },
  })
  useServerSeoMeta({
    author: 'author name',
    description: 'page description',
    keywords: 'vuejs, nuxtjs, html, css, javascript',
    themeColor: "#34495E",  
  })  

  onMounted(()=> {    // hydrating
    displayNotifier('Welcome 🎵', 2000)
    updateClientScreenPropertiesOnMounted()
    initClientAppPropertiesOnMounted()
    useEventListener('resize', ()=> { updateClientScreenPropertiesOnMounted() })
    useEventListener(window.matchMedia("(prefers-color-scheme:dark)"), 'change', ()=> {
      updateClientScreenPropertiesOnMounted() 
      appColorModeHandler()
    })
    // console.log(window.navigator.userAgent);
  })
  function initClientAppPropertiesOnMounted() {
    // console.log(useRoute().path);
    appStore.client_IsDarkViewport(appStore.clientScr.isDarkDevice)   // initialise viewport's color mode to follow system's color mode
  }
  function updateClientScreenPropertiesOnMounted() {   
    appStore.m_clientScrW()
    appStore.m_clientScrH()
    appStore.m_clientScrOrientation()
    appStore.m_clientScrRatioWH()
    appStore.m_clientScrFormFactor()
    appStore.m_clientScrIsMobile()
    appStore.m_clientScrIsMobileAndLandscape()
    appStore.m_clientScrIsDarkDevice()    
  }
</script>