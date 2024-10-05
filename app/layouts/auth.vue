<template>
  <div class="h-screen w-full">
    <div class="grid grid-cols-12 gap-3 h-full">
      <div class="col-span-6">
        <div class="flex items-center justify-center h-full">
          <div class="w-full max-w-sm space-y-5">
            <logo />
            <slot />
          </div>
        </div>
      </div>
      <div class="relative col-span-6 bg-cover bg-center" style="background-image: url('/images/jeswin-thomas-mVLIOmH5w3U-unsplash.jpg')">
        <div class="absolute top-0 left-0 w-full h-full bg-black opacity-30" />
        <div class="absolute top-0 left-0 w-full h-full">
          <div class="flex flex-col h-full">
            <div class="grow" />
            <h1 class="text-white text-5xl leading-tight font-bold font-inter p-10" style="backdrop-filter: blur(10px);">
              Unlock the Future of Education with Seamless Access and Control
            </h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
