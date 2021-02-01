<template>
    <!-- Desktop sidebar -->
    <aside
      x-transition:enter="transition ease-in-out duration-150"
      x-transition:enter-start="opacity-0 transform -translate-x-20"
      x-transition:enter-end="opacity-100"
      class="shadow-md z-20 hidden w-64 overflow-y-auto bg-white dark:bg-gray-800 md:block flex-shrink-0"
    >
      <div class="py-4 text-gray-500 dark:text-gray-800">
        <a
          class="ml-6 text-lg font-bold text-gray-800 dark:text-gray-200"
          href="#"
        >
        </a>
        <ul class="mt-6">
          <li
            class="relative pl-6 py-3 hover:bg-purple-700 transition-colors duration-150 hover:text-teal-100 dark:hover:text-teal-200"
            v-for="menu in menus"
            :key="menu.name"
            :class="[isActiveMenu(menu.name)
                      ? 'bg-purple-700 text-teal-100' : '']"
            
          >
            <div
              class="items-center justify-between w-full sm:inline-flex text-sm font-semibold"
              @click="setToggleMenu(menu.name)"
            >
              <template v-if="menu.hasChild">
                <span
                  class="absolute inset-y-0 left-0 w-1 bg-purple-500 rounded-tr-lg rounded-br-lg"
                  aria-hidden="true"
                >
                </span>
                 <div>
                  <i :class="[menu.icon]"></i>
                  <span class="ml-2 uppercase">{{ menu.name }} </span>
                </div>
                <i
                v-show="menu.hasChild"
                  :class="[
                    'right-0',
                    'pr-6',
                    'fas',
                    'text-right',
                    isActiveMenu(menu.name)
                      ? 'fa-chevron-down'
                      : 'fa-chevron-right',
                    'fa-sm',
                    'transition-500',
                  ]"
                ></i>
              </template> 
              <template v-else>
                <span
                  class="absolute inset-y-0 left-0 w-1 bg-purple-500 rounded-tr-lg rounded-br-lg"
                  aria-hidden="true"
                >
                </span>
                <NuxtLink :to="menu.label">
                  <i :class="[menu.icon]"></i>
                  <span class="ml-2 uppercase">{{ menu.name }} </span>
                </NuxtLink>
              </template>             
            </div>
            <ul class="mt-3" v-show="menu.hasChild && isActiveMenu(menu.name)">
              <li :class="['w-full','hover:bg-purple-800', isActiveSubMenu(children.name) ? 'bg-purple-900 shadow-lg' : '','relative pl-3 py-3']" :key="children.name" v-for="children in menu.children" @click="setToggleSubMenu(children.name)">
                  <div
                    class="items-center justify-between w-full sm:inline-flex text-sm font-semibold uppercase"
                  >
                   <NuxtLink :to="children.label">
                    <i :class="[children.icon]"></i>
                    <span class="uppercase">{{children.name}}</span>
                  </NuxtLink>
                  </div>
              </li>
          </ul>
          </li>
        </ul>
      </div>
    </aside>
    <!-- Backdrop -->
</template>

<script>
export default {
  data() {
    return {
      activeMenu: "dashboard",
      activeSubMenu: "",
      window: {
        height: 0,
        width: 0,
      },
      menus: [
        {
          name: "home",
          label: "dashboard",
          badgeLabel: "Badge",
          badgeColor: "red",
          icon: ["fas", "fa-home"],
          hasChild: false,
        },
        {
          name: "apps",
          label: "dashboard",
          icon: ["fas", "fa-boxes"],
          hasChild: true,
          isUpcoming: true,
          defaultChildrenIcon: ["fas", "fa-chevron-right"],
          children: [
            {
              name: "appCalendar",
              label: "dashboard",
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-calendar"],
              isUpcoming: true,
            },
            {
              name: "appChat",
              label: "dashboard",
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-comments"],
              isUpcoming: true,
            },
            {
              name: "appInbox",
              label: "dashboard",
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-envelope"],
              isUpcoming: true,
            },
            {
              name: "appScrumboard",
              label: "dashboard",
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-scroll"],
              isUpcoming: true,
            },
            {
              name: "appTodo",
              label: "dashboard",
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-tasks"],
              isUpcoming: true,
            },
          ],
        },
        {
          name: "cards",
          label: "cards",
          badgeLabel: "Upcoming",
          icon: ["fas", "fa-magic"],
          hasChild: false,
          isUpcoming: true,
        },
        {
          name: "pages",
          label: "dashboard",
          badgeLabel: "New",
          icon: ["fas", "fa-layer-group"],
          hasChild: true,
          defaultChildrenIcon: ["fas", "fa-chevron-right"],
          children: [
            {
              name: "pageLogin",
              label: "dashboard",
              icon: ["fas", "fa-sign-in-alt"],
            },
            {
              name: "pageRegister",
              label: "dashboard",
              icon: ["fas", "fa-user-plus"],
            },
            {
              name: "pageComingSoon",
              label: "dashboard",
              isUpcoming: true,
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-weight"],
            },
            {
              name: "pageUserProfile",
              label: "dashboard",
              isUpcoming: true,
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-user"],
            },
            {
              name: "pageInvoice",
              label: "dashboard",
              isUpcoming: true,
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-file-invoice"],
            },
            {
              name: "pageError404",
              label: "dashboard",
              isUpcoming: true,
              badgeLabel: "Upcoming",
              icon: ["fas", "fa-ban"],
            },
          ],
        },
      ],
    };
  },

  methods: {
    isActiveMenu(menu) {
      return menu === this.activeMenu ? true : false;
    },
    isActiveSubMenu(subMenu) {
      return subMenu === this.activeSubMenu ? true : false;
    },
    setToggleMenu(menu) {
      this.activeMenu = this.activeMenu == menu ? "" : menu;
    },
    setToggleSubMenu(subMenu) {
      this.activeSubMenu = this.activeSubMenu == subMenu ? "" : subMenu;
    },
}
}
</script>

<style lang="stylus" scoped>
</style>