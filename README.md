### Node.js: Make sure to use an even numbered version (18, 20, etc)
### final size is about 190 MB

- [Github repo](https://github.com/zulfidly/boilerplate-nuxt-vueuse-pinia-tailwind)

### Install Nuxt
- 
```
npx nuxi@latest init <project-name>
```
- ```cd <project-name>```
- ```npm install```

### Install VueUse
- ```npm i -D @vueuse/nuxt @vueuse/core```

### Install Tailwind CSS 
- ```npm install -D @nuxtjs/tailwindcss```
- ```npx tailwindcss init -p``` (bring tailwindcss.config.js into root folder)
- see ```/assets/style.css```
- see ```@nuxtjs/tailwindcss``` inside ```nuxt.config.ts```
- see ```tailwind.config.js```

### Install [Pinia](https://pinia.vuejs.org/ssr/nuxt.html)
- add ```overrides``` added to package.json
- ```npm install pinia @pinia/nuxt```
- ```export const useMainStorePinia = defineStore('appStore', {})```, dir: ```./composables/appStore.js``` 
- see ```@pinia/nuxt``` in nuxt.config.js
- see ```./composables/appStore.js```
- note: run ```npm run dev``` will remove the problem(highlighted red) for pinia in ```nuxt.config.ts```, or rename the file extension to ```.js```


```
npm run dev
```

