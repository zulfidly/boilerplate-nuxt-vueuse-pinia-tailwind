### Node.js: Make sure to use an even numbered version (18, 20, etc)
### final size is about 190 MB

- [Github repo](https://github.com/zulfidly/boilerplate-nuxt-vueuse-pinia-tailwind)

### Install [Nuxt](https://nuxt.com/)
```
npx nuxi@latest init n
```
- ```cd n```
- ```npm install```

### Install [VueUse](https://vueuse.org/)
```
npm i -D @vueuse/nuxt @vueuse/core
```

### Install [Tailwind CSS](https://tailwindcss.com/)
- [@nuxtjs/tailwindcss](https://tailwindcss.nuxtjs.org/)
```
npm install -D @nuxtjs/tailwindcss
```
- Bring tailwindcss.config.js into root folder, with codes below
```
npx tailwindcss init -p
```
- see ```/assets/style.css```
- see ```@nuxtjs/tailwindcss``` inside ```nuxt.config.ts```
- see ```tailwind.config.js```

### Install [Pinia](https://pinia.vuejs.org/ssr/nuxt.html)
- add ```overrides``` to package.json
```
"overrides": {
    "vue": "latest"
  }
```
```
npm install pinia @pinia/nuxt
```
- ```export const useMainStorePinia = defineStore('appStore', {})```, dir: ```./composables/appStore.js``` 
- see ```@pinia/nuxt``` in nuxt.config.js
- see ```./composables/appStore.js```
- note: run ```npm run dev``` will remove the problem(highlighted red) for pinia in ```nuxt.config.ts```, or rename the file extension to ```.js```


```
npm run dev
```
- to auto open browser :
```
npm run dev -- -o
```


