<script setup lang="ts"></script>

<template>
  <footer class="footer text-white py-8 sm:text-center">
    <div class="container mx-auto flex flex-col md:flex-row justify-between items-center px-4">
      <div class="flex flex-col items-center md:items-start mb-6 md:mb-0 text-center md:text-left w-full md:w-auto">
        <img src="../../assets/logo-1.png" alt="Logo" class="mb-4" />
        <h3 class="text-lg font-bold">{{ $t('contactus') }}</h3>
        <p class="text-sm">Regus – Arnhem, Business Park</p>
        <p class="text-sm">Meester B.M. Teldersstraat 7,</p>
        <p class="text-sm">6842 CT Arnhem</p>
        <p class="text-sm">Landjuweel 44, 3905 PH Veenendaal</p>
        <br>
        <p class="text-sm">info@werhere.nl</p>
        <p class="text-sm">(085) 7326225</p>
      </div>
      <div class="flex flex-col items-center md:items-start mb-6 md:mb-0 text-center md:text-left w-full md:w-auto">
        <h3 class="text-lg font-bold">{{ $t('quicklink') }}</h3>
        <ul class="list-none space-y-2">
          <li><a href="/" class="text-sm text-gray-400 hover:text-red-600">{{$t('home')}}</a></li>
          <li><a href="https://werhere.nl/" target="_blank" class="text-sm text-gray-400 hover:text-red-600">{{$t('website')}}</a></li>
          <li><a href="/create" class="text-sm text-gray-400 hover:text-red-600">{{$t('create')}}</a></li>
        </ul>
      </div>
      <div class="flex flex-col items-center md:items-start text-center md:text-left w-full md:w-auto">
        <h3 class="text-lg font-bold">Follow Us</h3>
        <div class="flex space-x-4 mt-2">
          <a href="https://www.youtube.com/channel/UC-DGrtHxchsxN9XnsgUYs9g/featured" target="_blank" class="text-gray-400 hover:text-red-600">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
              <path
                d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z" />
            </svg>
          </a>
          <a href="https://www.linkedin.com/company/werhere-nl/?originalSubdomain=nl" target="_blank" class="text-gray-400 hover:text-red-600">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
              <path
                d="M4.98 3.5c0 1.381-1.11 2.5-2.48 2.5s-2.48-1.119-2.48-2.5c0-1.38 1.11-2.5 2.48-2.5s2.48 1.12 2.48 2.5zm.02 4.5h-5v16h5v-16zm7.982 0h-4.968v16h4.969v-8.399c0-4.67 6.029-5.052 6.029 0v8.399h4.988v-10.131c0-7.88-8.922-7.593-11.018-3.714v-2.155z" />
            </svg>
          </a>
        </div>
      </div>
    </div>
    <div class="container mx-auto text-center mt-8 px-4">
      <p class="text-sm text-gray-400">&copy; {{$t('rights')}}.</p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: #f5f5f5;
  color: #000;
}

.footer a {
  transition: color 0.3s ease;
}

.footer a:hover {
  color: #da1e3c;
}
</style>
