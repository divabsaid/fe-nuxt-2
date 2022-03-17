<template>
  <div class="">
    <table style="width: 100%" class="border-collapse">
      <thead>
        <tr class="bg-gray-200 w-full">
          <th v-for="(col,i) in cols" :key="col" :class="'font-semibold text-xs leading-10 px-4 '+col.class " @click="sortTable(i)">
            {{ col.value }}
            <font-awesome-icon :icon="['fas', 'sort']" />
          </th>
        </tr>
      </thead>
      <tbody cellspacing="4">
        <tr v-for="(row,i) in get_rows()" :key="i" class="py-4 border-b border-gray-300">
          <td v-for="(r, j) in row" :key="j">
            <div :class="'px-4 text-sm '+ r.class">
              {{ r.value }}
            </div>
          </td>
        </tr>
      </tbody>
    </table>
    <div class="flex justify-end px-6 py-3">
      <div class="flex items-center">
        <p class="mr-2 text-xs">
          Rows per page:
        </p>
        <select v-model="elementsPerPage" class="text-xs" @change="change_element_per_page($event)">
          <option value="1">
            1
          </option>
          <option value="2">
            2
          </option>
          <option value="3">
            3
          </option>
        </select>

        <div class="mx-5 text-xs">
          {{ startNumber }}-{{ endNumber }} of {{ rows.length }}
        </div>
        <font-awesome-icon
          :icon="['fas', 'angle-left']"
          class="h-3 mx-4"
          @click="change_page(currentPage-1)"
        />
        <font-awesome-icon
          :icon="['fas', 'angle-right']"
          class="h-3 mx-4"
          @click="change_page(currentPage+1)"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'TableComponent',
  data () {
    return {
      currentPage: 1,
      elementsPerPage: 1,
      ascending: false,
      sortColumn: '',
      cols: [
        {
          value: 'ORDER REF',
          class: 'text-left'
        }, {
          value: 'CUSTOMER',
          class: 'text-left'
        }, {
          value: 'DATE',
          class: 'text-center'
        }, {
          value: 'STATUS',
          class: 'text-left'
        }
      ],
      rows: [
        [
          {
            value: 'CDD1049',
            class: 'text-left'
          },
          {
            value: 'Ekaterina Tankova',
            class: 'text-left'
          },
          {
            value: '12/04/2019',
            class: 'text-center'
          },
          {
            value: 'Pending',
            class: 'mx-auto font-normal text-white text-sm py-0.5 rounded-full my-2 text-center w-max ' + (this.elementsPerPage > 1 ? 'bg-red-500' : this.elementsPerPage > 2 ? 'bg-yellow-500' : 'bg-green-500')
          }
        ],
        [
          {
            value: 'CDD1049',
            class: 'text-left'
          },
          {
            value: 'Ekaterina Tankova',
            class: 'text-left'
          },
          {
            value: '12/04/2019',
            class: 'text-center'
          },
          {
            value: 'Pending',
            class: 'mx-auto font-normal text-white text-sm py-1 rounded-full m-2 text-center w-max px-3 ' + (this.elementsPerPage > 1 ? 'bg-red-500' : this.elementsPerPage > 2 ? 'bg-yellow-500' : 'bg-green-500')
          }
        ], [
          {
            value: 'CDD1049',
            class: 'text-left'
          },
          {
            value: 'Ekaterina Tankova',
            class: 'text-left'
          },
          {
            value: '12/04/2019',
            class: 'text-center'
          },
          {
            value: 'Pending',
            class: 'mx-auto font-normal text-white text-sm py-0.5 rounded-full my-2 text-center w-max ' + (this.elementsPerPage > 1 ? 'bg-red-500' : this.elementsPerPage > 2 ? 'bg-yellow-500' : 'bg-green-500')
          }
        ]

      ]

    }
  },
  computed: {
    startNumber () {
      return parseInt(((this.currentPage - 1) * this.elementsPerPage) + 1)
    },
    endNumber () {
      return parseInt(parseInt((this.currentPage - 1) * this.elementsPerPage) + parseInt(this.elementsPerPage)) >= this.rows.length ? this.rows.length : parseInt(parseInt((this.currentPage - 1) * this.elementsPerPage) + parseInt(this.elementsPerPage))
    }
  },
  methods: {
    sortTable: function sortTable (col) {
      if (this.sortColumn === col) {
        this.ascending = !this.ascending
      } else {
        this.ascending = true
        this.sortColumn = col
      }

      const ascending = this.ascending

      this.rows.sort(function (a, b) {
        if (a[col].value > b[col].value) {
          return ascending ? 1 : -1
        } else if (a[col].value < b[col].value) {
          return ascending ? -1 : 1
        }
        return 0
      })
    },
    num_pages: function numPages () {
      return Math.ceil(this.rows.length / this.elementsPerPage)
    },
    get_rows: function getRows () {
      const start = (this.currentPage - 1) * this.elementsPerPage
      const end = start + this.elementsPerPage
      return this.rows.slice(start, end)
    },
    change_page: function changePage (page) {
      if (page > 0 && page <= this.num_pages()) {
        this.currentPage = page
      }
    },
    change_element_per_page: function changeElementPerPage (event) {
      this.elementsPerPage = event.target.value
      this.get_rows()
      this.num_pages()
      this.change_page(1)
    }
  }
}
</script>
<style scoped>

</style>
