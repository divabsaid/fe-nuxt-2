<template>
  <div class="flex">
    <div class="flex-none w-72 bg-gray-500">
      <div class="border-b">
        <img
          class="h-8 w-8 m-4"
          src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
          alt=""
        >
      </div>
      <div class="ml-2 mt-2">
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'house']"
            class="p-3 w-5"
          />
          <p>Dashboard</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'user-group']"
            class="p-3 w-5"
          />
          <p>Customers</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'bag-shopping']"
            class="p-3 w-5"
          />
          <p>Products</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'user']"
            class="p-3 w-5"
          />
          <p>Account</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'gear']"
            class="p-3 w-5"
          />
          <p>Settings</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'lock']"
            class="p-3 w-5"
          />
          <p>Login</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'user-plus']"
            class="p-3 w-5"
          />
          <p>Register</p>
        </div>
        <div class="flex items-center">
          <font-awesome-icon
            :icon="['fas', 'circle-xmark']"
            class="p-3 w-5"
          />
          <p>Error</p>
        </div>
      </div>
    </div>
    <div class="bg-gray-100 flex flex-col w-full">
      <div class="bg-gray-300 flex justify-between items-center h-12">
        <div class="ml-4">
          <font-awesome-icon
            :icon="['fas', 'magnifying-glass']"
          />
        </div>
        <div class="flex mr-4 justify-between w-32 items-center">
          <font-awesome-icon
            :icon="['fas', 'user-group']"
          />
          <font-awesome-icon
            :icon="['fas', 'bell']"
          />
          <img
            class="inline-block h-8 w-8 rounded-full"
            src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
            alt=""
          >
        </div>
      </div>
      <div class="grid grid-cols-4 gap-4 m-4">
        <div class="bg-white rounded-lg p-4">
          <div class="flex flex-row justify-between items-center mb-4">
            <div class="">
              <p class="text-xs uppercase font-semibold mb-2">
                Budget
              </p>
              <p class="text-2xl font-bold">
                $24k
              </p>
            </div>
            <div class=" w-12 h-12 flex items-center justify-center rounded-full bg-red-400">
              <font-awesome-icon
                :icon="['fas', 'money-bill']"
                class="text-white"
              />
            </div>
          </div>
          <p class="text-xs mx-1">
            <font-awesome-icon
              :icon="['fas', 'caret-down']"
              class="text-red-500 mr-3"
            /> <span>12%</span> Since last month
          </p>
        </div>
        <div class="bg-white rounded-lg p-4">
          <div class="flex flex-row justify-between items-center mb-4">
            <div class="">
              <p class="text-xs uppercase font-semibold mb-2">
                Total Customers
              </p>
              <p class="text-2xl font-bold">
                1,6k
              </p>
            </div>
            <div class=" w-12 h-12 flex items-center justify-center rounded-full bg-red-400">
              <font-awesome-icon
                :icon="['fas', 'user-group']"
                class="text-white"
              />
            </div>
          </div>
          <p class="text-xs mx-1">
            <font-awesome-icon
              :icon="['fas', 'caret-down']"
              class="text-red-500 mr-3"
            /> <span>12%</span> Since last month
          </p>
        </div>

        <div class="bg-white rounded-lg p-4">
          <div class="flex flex-row justify-between items-center mb-4">
            <div class="">
              <p class="text-xs uppercase font-semibold mb-2">
                Tasks Progress
              </p>
              <p class="text-2xl font-bold">
                75.5%
              </p>
            </div>
            <div class=" w-12 h-12 flex items-center justify-center rounded-full bg-red-400">
              <font-awesome-icon
                :icon="['fas', 'user-group']"
                class="text-white"
              />
            </div>
          </div>
          <div class="bg-gray-200 rounded-full h-1 w-full">
            <div class="bg-gray-500 h-1 w-3/4" />
          </div>
        </div>

        <div class="bg-white rounded-lg p-4">
          <div class="flex flex-row justify-between items-center mb-4">
            <div class="">
              <p class="text-xs uppercase font-semibold mb-2">
                Total Profit
              </p>
              <p class="text-2xl font-bold">
                $23k
              </p>
            </div>
            <div class=" w-12 h-12 flex items-center justify-center rounded-full bg-red-400">
              <font-awesome-icon
                :icon="['fas', 'dollar-sign']"
                class="text-white"
              />
            </div>
          </div>
          <p class="text-xs mx-1">
            <font-awesome-icon
              :icon="['fas', 'caret-down']"
              class="text-red-500 mr-3"
            /> <span>12%</span> Since last month
          </p>
        </div>

        <div class="col-span-3 bg-white rounded-lg py-5">
          <div class="flex justify-between border-b-2 pb-4 px-4">
            <p class="font-semibold">
              Latest Sales
            </p>
            <div>
              <select class="text-xs">
                <option value="">
                  Last 7 days
                </option>
              </select>
            </div>
          </div>
          <BarChart :data="chartdata" :height="200" class="py-4 px-8" />
          <div class="flex border-t-2 justify-end px-6 pt-4 text-xs">
            <p class="mr-4 ">
              View All
            </p>
            <font-awesome-icon
              :icon="['fas', 'caret-right']"
              class="mt-0.5"
            />
          </div>
        </div>
        <div class="bg-white rounded-lg py-5 flex flex-col">
          <p class="font-semibold border-b-2 pb-4 px-6">
            Traffic by Device
          </p>
          <DoughnutChart :data="chartdata" :height="300" class="my-4" />
          <div class="flex justify-around mx-2">
            <div class="flex flex-col items-center">
              <font-awesome-icon
                :icon="['fas', 'display']"
                class=""
              />
              <p class="font-light text-xs mt-1">
                Desktop
              </p>
              <p class="font-bold text-2xl mt-1">
                63%
              </p>
            </div>
            <div class="flex flex-col items-center">
              <font-awesome-icon
                :icon="['fas', 'tablet-screen-button']"
                class=""
              />
              <p class="font-light text-xs mt-1">
                Tablet
              </p>
              <p class="font-bold text-2xl mt-1">
                15%
              </p>
            </div>
            <div class="flex flex-col items-center">
              <font-awesome-icon
                :icon="['fas', 'mobile-screen-button']"
                class=""
              />
              <p class="font-light text-xs mt-1">
                Mobile
              </p>
              <p class="font-bold text-2xl mt-1">
                22%
              </p>
            </div>
          </div>
        </div>

        <div class="bg-white rounded-lg">
          <p class="font-semibold border-b-2 py-4 px-6">
            Traffic by Device
          </p>
          <div class="flex justify-beetween items-center px-2 border-b-2">
            <img
              class="h-8 w-8 m-3"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
              alt=""
            >
            <div class="w-full">
              <p class="text-sm">
                Dropbox
              </p>
              <p class="text-xs">
                Updated 2 hours ago
              </p>
            </div>
            <font-awesome-icon
              :icon="['fas', 'ellipsis-vertical']"
              class="m-3"
            />
          </div>
          <div class="flex justify-beetween items-center px-2 border-b-2">
            <img
              class="h-8 w-8 m-3"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
              alt=""
            >
            <div class="w-full">
              <p class="text-sm">
                Medium Corporation
              </p>
              <p class="text-xs">
                Updated 2 hours ago
              </p>
            </div>
            <font-awesome-icon
              :icon="['fas', 'ellipsis-vertical']"
              class="m-3"
            />
          </div>
          <div class="flex justify-beetween items-center px-2 border-b-2">
            <img
              class="h-8 w-8 m-3"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
              alt=""
            >
            <div class="w-full">
              <p class="text-sm">
                Slack
              </p>
              <p class="text-xs">
                Updated 2 hours ago
              </p>
            </div>
            <font-awesome-icon
              :icon="['fas', 'ellipsis-vertical']"
              class="m-3"
            />
          </div>
          <div class="flex justify-beetween items-center px-2 border-b-2">
            <img
              class="h-8 w-8 m-3"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
              alt=""
            >
            <div class="w-full">
              <p class="text-sm">
                Lyft
              </p>
              <p class="text-xs">
                Updated 2 hours ago
              </p>
            </div>
            <font-awesome-icon
              :icon="['fas', 'ellipsis-vertical']"
              class="m-3"
            />
          </div>
          <div class="flex justify-beetween items-center px-2 border-b-2">
            <img
              class="h-8 w-8 m-3"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
              alt=""
            >
            <div class="w-full">
              <p class="text-sm">
                Github
              </p>
              <p class="text-xs">
                Updated 2 hours ago
              </p>
            </div>
            <font-awesome-icon
              :icon="['fas', 'ellipsis-vertical']"
              class="m-3"
            />
          </div>
          <div class="flex justify-end py-4 px-8 text-xs">
            <p class="mr-4 ">
              View All
            </p>
            <font-awesome-icon
              :icon="['fas', 'caret-right']"
              class="mt-0.5"
            />
          </div>
        </div>
        <div class="col-span-3 bg-white rounded-lg">
          <p class="font-semibold py-4 px-6">
            Latest Orders
          </p>
          <Table />
        </div>
      </div>
      <div class="border-t-2 my-4 mx-8">
        <p class="text-xs mt-2">
          &copy; Devias Io. 2021
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DashboardPage',
  data: () => ({
    chartdata: {
      labels: ['January', 'February'],
      datasets: [
        {
          label: 'Data One',
          backgroundColor: '#f87979',
          data: [40, 20]
        }
      ]
    },
    options: {
    }
  })
}
</script>
