<template>
  <main>
    <div class="container mx-auto px-5">
      <div class="grid grid-cols-8 gap-4 my-2">
        <div class="col-span-1 flex flex-col">
          <img src="~assets/pickans_beta_logo.png" class="w-full py-2" />
          <button class="flex justify-center items-center my-5 bg-blue-400 hover:bg-blue-600 text-white font-semibold hover:text-white py-1 px-2 border border-blue-300 hover:border-transparent rounded">
            <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mr-2" alt="icon">
            <small>ASK</small>
          </button>
          <ul>
            <li v-for="item in menuItems" :key="item.id">
              <a
                class="flex items-center py-2 hover:underline font-semibold text-sm cursor-pointer"
                :class="selectedMenu === item.id ? 'text-blue-400' : 'text-gray-700'"
                @click="selectedMenu = item.id"
              >
                <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mr-2" alt="icon">
                {{ item.title }}
              </a>
            </li>
          </ul>
        </div>
        <div class="col-span-5 flex-col">
          <div class="rounded-md bg-white border border-gray-200 p-4">
            <div class="flex justify-between">
              <div class="flex flex-col">
                <strong class="text-2xl">Community Feed</strong>
                <small>Recent questions from community</small>
              </div>
              <div class="flex items-center">
                <button class="flex bg-transparent hover:bg-blue-300 text-blue-400 font-semibold hover:text-white py-1 px-2 border border-blue-300 hover:border-transparent rounded-md">
                  <img src="https://via.placeholder.com/25?text=icon" class="rounded-3xl mx-auto mr-1" alt="icon">
                  Personalize this feed
                </button>
              </div>
            </div>
          </div>
          <div class="rounded-md bg-white border border-gray-200 pl-4 pr-1 py-2 my-2">
            <div class="flex justify-between">
              <ul class="flex">
                <li class="mr-6">
                  <a
                     class="hover:text-blue-400 flex items-center cursor-pointer"
                     :class="listFeed === 'best' ? 'text-blue-400' : 'text-black'"
                     @click="listFeed = 'best'"
                  >
                    <img src="https://via.placeholder.com/20?text=icon" class="rounded-3xl mx-auto mr-1" alt="icon">
                    <small class="font-semibold">Best</small>
                  </a>
                </li>
                <li class="mr-6">
                  <a
                     class="hover:text-blue-400 flex items-center cursor-pointer"
                     :class="listFeed === 'featured' ? 'text-blue-400' : 'text-black'"
                     @click="listFeed = 'featured'"
                  >
                    <img src="https://via.placeholder.com/20?text=icon" class="rounded-3xl mx-auto mr-1" alt="icon">
                    <small class="font-semibold">Featured</small>
                  </a>
                </li>
                <li class="mr-6">
                  <a
                    class="hover:text-blue-400 flex items-center cursor-pointer"
                    :class="listFeed === 'recent' ? 'text-blue-400' : 'text-black'"
                    @click="listFeed = 'recent'"
                  >
                    <img src="https://via.placeholder.com/20?text=icon" class="rounded-3xl mx-auto mr-1" alt="icon">
                    <small class="font-semibold">Recent</small>
                  </a>
                </li>
              </ul>
              <div class="flex items-center">
                <img src="https://via.placeholder.com/20?text=icon" class="rounded-3xl mx-auto mr-1" alt="icon">
              </div>
            </div>
          </div>
          <div class="rounded-md bg-white border border-gray-200 my-2">
            <slot></slot>
          </div>
        </div>
        <div class="col-span-2 flex-col">
          <div class="flex justify-between rounded-md bg-white border border-gray-200 px-4">
            <svg width="24" height="24" fill="none" class="group-hover:text-gray-500 transition-colors duration-200 my-auto"><path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg>
            <input type="text" class="form-input px-4 py-3 rounded-full w-4/5 mx-1" placeholder="Search Pickans">
            <div class="text-gray-400 text-sm leading-5 py-0.5 px-1.5 border border-gray-300 rounded-md my-3 font-bold text-xl">#</div>
          </div>
          <div class="rounded-md bg-white border border-gray-200 mt-2">
            <div class="flex justify-between p-4">
              <strong>Top questions</strong>
              <div class="flex justify-between w-2/5 my-auto">
                <small>1w</small>
                <small>1m</small>
                <small>3m</small>
                <small>6m</small>
              </div>
            </div>
            <hr>
            <div class="flex flex-col p-4">
              <nuxt-link to="#" v-for="item in questions" :key="item" class="mb-2">
                <strong class="sm:font-bold text-xs">{{ item.title }}</strong>
                <div class="flex text-xs">
                  <span class="mr-3">{{ item.author }}</span>
                  <span class="mx-3">{{ item.likes }}</span>
                  <span class="mx-3">{{ item.comments }}</span>
                </div>
              </nuxt-link>
            </div>
          </div>
          <div class="rounded-md bg-white border border-gray-200 mt-2">
            <div class="flex justify-between p-4">
              <strong>Trending experts</strong>
            </div>
            <hr>
            <div class="flex flex-col p-4">
              <nuxt-link to="#" v-for="item in trendExperts" :key="item.id" class="flex justify-between">
                <div class="flex my-auto items-center">
                  <strong class="text-gray-300">{{ item.id >= 10 ? item.id : "0" + item.id }}</strong>
                  <img src="https://via.placeholder.com/40?text=user" class="h-8 w-8 rounded-full ring-1 ring-gray-300 mx-2" alt="user">
                  <strong class="text-sm">{{ item.name }}</strong>
                </div>
                <div class="text-sm leading-5 py-0.5 px-1.5 border border-gray-300 rounded-md my-3 font-bold text-xl">+</div>
              </nuxt-link>
            </div>
            <hr>
            <div class="p-4 flex">
              <img src="https://via.placeholder.com/20?text=user" class="rounded-3xl mx-2" alt="user">
              <small class="font-bold text-gray-300">Explore trending experts</small>
            </div>
          </div>
          <div class="rounded-md bg-white border border-gray-200 mt-2">
            <div class="flex justify-between p-4">
              <strong>Tags to follow</strong>
            </div>
            <hr>
            <div class="flex flex-col p-4">
              <div class="grid grid-cols-2 max-h-80 overflow-y-scroll">
                <nuxt-link to="#" v-for="item in tagsToFollow" :key="item.id" class="flex justify-between items-baseline">
                  <div class="flex-col items-center text-center mx-auto my-1">
                    <img src="https://via.placeholder.com/40?text=icon" class="rounded-3xl mx-auto" alt="icon">
                    <span class="text-xs">{{ item.name }}</span>
                  </div>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
export default {
  name: "PageBase",
  data(){
    return {
      listFeed: 'best',
      selectedMenu: 1,
      questions: [
        {
          title: 'Convertional Comments',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
        {
          title: 'JavaScript Patterns [Ch.1:Introduction]',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
        {
          title: 'Convertional Comments',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
        {
          title: 'JavaScript Patterns [Ch.1:Introduction]',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
        {
          title: 'Convertional Comments',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
        {
          title: 'JavaScript Patterns [Ch.1:Introduction]',
          author: 'Abdallah Hemdan',
          likes: 237,
          comments: 6
        },
      ],
      trendExperts: [
        {
          id:1,
          name: "Chris Miller"
        },
        {
          id:2,
          name: "Brayan Arriyeta Alfaro"
        },
        {
          id:3,
          name: "Victoria Lo"
        },
        {
          id:4,
          name: "Ken Bony"
        }
      ],
      tagsToFollow: [
        {
          id:1,
          name: "Talk of the town"
        },
        {
          id:2,
          name: "Self Starter"
        },
        {
          id:3,
          name: "#2Articles1Week Challenge"
        }
      ],
      menuItems: [
        {
          id: 1,
          title: 'My Feed'
        },
        {
          id: 2,
          title: 'Explore'
        },
        {
          id: 3,
          title: 'Category'
        },
        {
          id: 4,
          title: 'Experts'
        },
        {
          id: 5,
          title: 'Saved'
        },
        {
          id: 6,
          title: 'Search'
        },
        {
          id: 7,
          title: 'More'
        }
      ]
    }
  }
}
</script>
<style scoped>
</style>
