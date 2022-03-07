<template>
  <div class="relative flex items-top justify-center min-h-screen bg-gray-200 sm:items-center sm:pt-0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <div class="">
      <a class="flex justify-center pt-8 sm:pt-0" href="https://nuxtjs.org" target="_blank">
        <svg width="218" height="45" viewBox="0 0 159 30" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M55.5017 6.81866H60.1727L70.0719 22.9912V6.81866H74.3837V29.7345H69.7446L59.8135 13.5955V29.7345H55.5017V6.81866Z"
            fill="#003543"/>
          <path
            d="M93.657 29.7344H89.6389V27.1747C88.7241 28.9761 86.8628 29.9904 84.5113 29.9904C80.7869 29.9904 78.3684 27.3059 78.3684 23.4423V13.2339H82.3865V22.5976C82.3865 24.8566 83.7594 26.4276 85.8171 26.4276C88.0712 26.4276 89.6389 24.6598 89.6389 22.2377V13.2339H93.657V29.7344Z"
            fill="#003543"/>
          <path
            d="M107.64 29.7344L103.784 24.2342L99.9291 29.7344H95.6492L101.596 21.1242L96.1074 13.2339H100.485L103.784 17.9821L107.051 13.2339H111.461L105.94 21.1242L111.886 29.7344H107.64Z"
            fill="#003543"/>
          <path
            d="M120.053 8.25848V13.2339H124.627V16.6063H120.053V24.7974C120.053 25.0725 120.162 25.3363 120.356 25.531C120.55 25.7257 120.813 25.8353 121.087 25.8357H124.627V29.728H121.98C118.386 29.728 116.035 27.6323 116.035 23.9687V16.6095H112.801V13.2339H114.83C115.776 13.2339 116.327 12.6692 116.327 11.7349V8.25848H120.053Z"
            fill="#003543"/>
          <path
            d="M134.756 24.5446V6.81866H139.066V23.1864C139.066 27.6067 136.943 29.7345 133.349 29.7345H128.332V25.8421H133.461C133.804 25.8421 134.134 25.7054 134.377 25.4621C134.619 25.2188 134.756 24.8888 134.756 24.5446Z"
            fill="#003543"/>
          <path
            d="M141.649 22.0409H145.799C146.029 24.6006 147.728 26.2308 150.472 26.2308C152.923 26.2308 154.623 25.2501 154.623 23.2199C154.623 18.3085 142.331 21.7129 142.331 12.9395C142.334 9.17515 145.568 6.55945 150.215 6.55945C155.05 6.55945 158.317 9.34153 158.516 13.6306H154.388C154.193 11.6341 152.632 10.2918 150.207 10.2918C147.953 10.2918 146.548 11.3397 146.548 12.9427C146.548 18.0173 159 14.2226 159 23.1576C159 27.4131 155.504 30 150.474 30C145.279 30 141.882 26.8563 141.654 22.0441"
            fill="#003543"/>
          <path
            d="M24.7203 29.704H41.1008C41.6211 29.7041 42.1322 29.5669 42.5828 29.3061C43.0334 29.0454 43.4075 28.6704 43.6675 28.2188C43.9275 27.7672 44.0643 27.2549 44.0641 26.7335C44.0639 26.2121 43.9266 25.6999 43.6662 25.2485L32.6655 6.15312C32.4055 5.70162 32.0315 5.32667 31.581 5.06598C31.1305 4.8053 30.6195 4.66805 30.0994 4.66805C29.5792 4.66805 29.0682 4.8053 28.6177 5.06598C28.1672 5.32667 27.7932 5.70162 27.5332 6.15312L24.7203 11.039L19.2208 1.48485C18.9606 1.03338 18.5864 0.658493 18.1358 0.397853C17.6852 0.137213 17.1741 0 16.6538 0C16.1336 0 15.6225 0.137213 15.1719 0.397853C14.7213 0.658493 14.3471 1.03338 14.0868 1.48485L0.397874 25.2485C0.137452 25.6999 0.000226653 26.2121 2.8053e-07 26.7335C-0.000226092 27.2549 0.136554 27.7672 0.396584 28.2188C0.656614 28.6704 1.03072 29.0454 1.48129 29.3061C1.93185 29.5669 2.44298 29.7041 2.96326 29.704H13.2456C17.3195 29.704 20.3239 27.9106 22.3912 24.4118L27.4102 15.7008L30.0986 11.039L38.1667 25.0422H27.4102L24.7203 29.704ZM13.0779 25.0374L5.9022 25.0358L16.6586 6.36589L22.0257 15.7008L18.4322 21.9401C17.0593 24.2103 15.4996 25.0374 13.0779 25.0374Z"
            fill="#00DC82"/>
        </svg>
      </a>
      <b-modal :id="infoModal.id" size="xl" :title="infoModal.title" hide-footer @hide="resetInfoModal">
        <pre>{{ infoModal.content }}</pre>
        <b-form @submit="onSubmit" @reset="onReset">
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              placeholder="Enter email"
              required
            />
          </b-form-group>

          <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
            <b-form-input
              id="input-2"
              v-model="form.name"
              placeholder="Enter name"
              required
            />
          </b-form-group>

          <b-form-group id="input-group-3" label="Gender:" label-for="input-3">
            <b-form-select
              id="input-3"
              v-model="form.gender"
              placeholder="Select Gender"
              required
            >
              <b-form-select-option value="male">Male</b-form-select-option>
              <b-form-select-option value="female">Female</b-form-select-option>
            </b-form-select>
          </b-form-group>

          <b-form-group id="input-group-4" label="Status" v-slot="{ ariaDescribedby }">
            <b-form-select
              id="input-4"
              v-model="form.status"
              placeholder="Select Status"
              required
            >
              <b-form-select-option value="active">Active</b-form-select-option>
              <b-form-select-option value="inactive">Inactive</b-form-select-option>
            </b-form-select>
          </b-form-group>
          <hr>
          <br>

          <b-form-group id="input-group-5"  >
            <b-row>
              <b-col>Daftar Post</b-col>
              <b-col align="right"><b-button variant="success" @click="$root.$emit('bv::show::modal', postModal)">Buat Post</b-button></b-col>
            </b-row>
            <b-row>
              <b-col>
                <b-table
                  id="my-table"
                  :items="itemPosts"
                  :fields="columnPosts"
                  :busy="loadings"
                  :filter="filter"
                  :tbody-td-class="rowClass"
                  :per-page="perPage"
                  select-mode="multi"
                  selectable
                  fixed
                  class="text-left"
                  :current-page="currentPage"
                  caption-top
                  @row-selected="onRowSelected"
                >
                  <template #table-caption>
                    <b-row>
                      <b-col cols="2">
                        <b-form-select v-model="perPage" :options="options"/>
                      </b-col>
                      <b-col>
                        <b-input-group>
                          <b-form-input
                            id="filter-input"
                            v-model="filter"
                            type="search"
                            placeholder="Search"
                          />

                        </b-input-group>
                      </b-col>
                      <b-col cols="2" class="text-center">
                        <b-button variant="danger" @click="onDelete(1)">Delete</b-button>
                      </b-col>
                    </b-row>
                  </template>

                  <template #cell(body)="row">
                    <TuiEditorViewer
                      :value="row.item.body"
                    />
                  </template>
                </b-table>
              </b-col>
            </b-row>
          </b-form-group>
          <hr>
          <br>
          <b-col align="right">
            <b-button type="submit" variant="primary">Update</b-button>
          </b-col>
        </b-form>
      </b-modal>
      <b-modal :id="postModal" size="xl" title="Dialog Box Buat Post" @ok="onSubmitPost" @show="posts.body='',posts.title=''">
        <b-form-group id="input-group-1" label="Title:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="posts.title"
            placeholder="Enter Title"
            required
          />
        </b-form-group>
          <TuiEditor v-model="posts.body" />
          <hr>
          <br>
        <template #modal-footer="{ ok, cancel }">
          <!-- Emulate built in modal footer ok and cancel button actions -->
          <b-button  @click="cancel()">
            Cancel
          </b-button>
          <b-button variant="danger" @click="ok()">
            OK
          </b-button>
        </template>
      </b-modal>
      <b-modal
        id="modal-new-user"
        v-model="modalnewuser"
        hide-footer
        centered
        @close="!modalnewuser"
        title="Form Daftar Pengguna Baru"
        @show="onReset"
        @hidden="onReset"
        @hide="!modalnewuser"
      >
        <b-form @submit="onSubmit" @reset="onReset">
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              placeholder="Enter email"
              required
            />
          </b-form-group>

          <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
            <b-form-input
              id="input-2"
              v-model="form.name"
              placeholder="Enter name"
              required
            />
          </b-form-group>

          <b-form-group id="input-group-3" label="Gender:" label-for="input-3">
            <b-form-select
              id="input-3"
              v-model="form.gender"
              placeholder="Select Gender"
              required
            >
              <b-form-select-option value="male">Male</b-form-select-option>
              <b-form-select-option value="female">Female</b-form-select-option>
            </b-form-select>
          </b-form-group>

          <b-form-group id="input-group-4" label="Status" v-slot="{ ariaDescribedby }">
            <b-form-select
              id="input-4"
              v-model="form.status"
              placeholder="Select Status"
              required
            >
              <b-form-select-option value="active">Active</b-form-select-option>
              <b-form-select-option value="inactive">Inactive</b-form-select-option>
            </b-form-select>
          </b-form-group>
        <hr>
          <br>
          <b-col align="right">
          <b-button type="submit" variant="primary">Submit</b-button>
          <b-button type="reset" variant="danger">Reset</b-button>
          </b-col>
        </b-form>
      </b-modal>
      <b-modal v-model="modal_alert" centered @hide="!modal_alert" hide-backdrop content-class="shadow" :header-bg-variant="alerts" title="Alert">
        <p class="my-2">
         {{ alerts_message }}
        </p>
      </b-modal>
      <b-modal v-model="modal_confirm" header-text-variant="light" centered @ok="actDelete" @hide="!modal_confirm" header-bg-variant="danger" hide-backdrop content-class="shadow" title="Confirm Delete">
        <p class="my-2">
          are you sure you want to delete
        </p>
        <template #modal-footer="{ ok, cancel }">
          <!-- Emulate built in modal footer ok and cancel button actions -->
          <b-button  @click="cancel()">
            Cancel
          </b-button>
          <b-button variant="danger" @click="ok()">
            OK
          </b-button>
        </template>
      </b-modal>

      <div class="mt-8 bg-white overflow-hidden shadow sm:rounded-lg p-6">
        <b-row>
          <b-col>
            <h2 class="text-2xl leading-7 font-semibold">
              DAFTAR PENGGUNA
            </h2>
          </b-col>
          <b-col class="text-right">
            <b-button variant="success" @click=" modalnewuser = !modalnewuser, isnew=true">Buat Pengguna</b-button>
          </b-col>
        </b-row>
        <b-row class="mt-3 text-gray-600">
          <b-col>
            <b-table
              id="my-table"
              :items="items"
              :fields="column"
              :busy="loadings"
              :filter="filter"
              :tbody-td-class="rowClass"
              :per-page="perPage"
              select-mode="multi"
              selectable
              :current-page="currentPage"
              caption-top
              @row-selected="onRowSelected"
            >
                <template #table-caption>
                  <b-row>
                    <b-col cols="2">
                      <b-form-select v-model="perPage" :options="options"/>
                    </b-col>
                    <b-col>
                      <b-input-group>
                        <b-form-input
                          id="filter-input"
                          v-model="filter"
                          type="search"
                          placeholder="Search"
                        />

                      </b-input-group>
                    </b-col>
                    <b-col cols="2" class="text-center">
                      <b-button variant="danger" @click="onDelete(0)">Delete</b-button>
                    </b-col>
                  </b-row>
              </template>
              <template #table-busy>
                <div v-show="loadings" class="text-center text-danger ">
                  <b-spinner class="align-middle"/>
                  <strong>Loading...</strong>
                </div>
              </template>
              <template #cell(status)="row">
                <b-td :variant="row.item.status === 'active' ? 'success' : 'danger' ">{{row.item.status}}</b-td>
              </template>
              <template #cell(actions)="row">
                <b-button size="sm" variant="info" @click="info(row.item, row.index, $event.target)" class="mr-1">
                  View / Update
                </b-button>
              </template>
            </b-table>
            <b-pagination
              v-model="currentPage"
              :total-rows="rows"
              :per-page="perPage"
              aria-controls="my-table"
              align="center"
            />
          </b-col>
        </b-row>

        <p class="mt-4 pt-4 text-gray-800 border-t border-dashed">
          By Awaludin Ramdani
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'IndexPage',
    data: () => ({
      alerts:'',
      alerts_message:'',
      modal_alert:false,
      modal_confirm:false,
      form:{name:null, email:null, gender:null, status:null, id:null},
      posts:{user_id:null,title:null,body:null},
      column: [
        {
          key: 'id',
          label: "ID",
          sortable: true
        },
        {
          key: 'name',
          label: "NAME",
          sortable: true
        },
        {
          key: 'email',
          label: "EMAIL",
          sortable: true
        },
        {
          key: 'gender',
          label: "GENDER",
          sortable: true
        },
        {
          key: 'status',
          label: "STATUS",
          sortable: true,
        },
        {key: 'actions', label: 'Actions'}
      ],
      columnPosts: [
        {
          key: 'id',
          label: "ID",
          sortable: true
        },
        {
          key: 'title',
          label: "TITLE",
          sortable: true
        },
        {
          key: 'body',
          label: "BODY",
          sortable: true
        }
      ],
      modalnewuser: false,
      filter: null,
      loadings: true,
      selected: [],
      items: [],
      itemPosts: [],
      isnew: true,
      deluser: true,
      perPage: 5,
      options: [
        {value: 5, text: '5'},
        {value: 10, text: '10'},
        {value: 20, text: '20'},
        {value: 50, text: '50'},
        {value: 100, text: '100'},
      ],
      infoModal: {
        id: 'info-modal',
        title: '',
        content: ''
      },
      postModal:"modal",
      currentPage: 1,
    }),

    methods: {
      onDelete(ids: number){
        this.deluser = ids === 0
        if(this.selected.length <= 0){
          this.alerts = 'warning'
          this.alerts_message = 'No selected data'
          this.modal_alert = true
          return;
        }
        this.modal_confirm = true
      },

      async listpost(){
        this.loadings = true
        const ip = await this.$axios.get(`users/${this.form.id}/posts`)
        this.itemPosts = ip.data
        this.loadings = false
      },

      async actDelete(){
        this.loadings = true
        for(let i = 0; i < this.selected.length; i++){
          let delet = this.deluser ? await this.$axios.$delete(`users/${this.selected[i].id}`) : await this.$axios.$delete(`posts/${this.selected[i].id}`)
          if(!delet){
            this.alerts = 'success'
            this.alerts_message = 'success'
            this.modal_alert = true
          }else{
            this.alerts = 'danger'
            this.alerts_message = `Failed delete id ${this.selected[i].id}`
            this.modal_alert = true
          }
        }
        await this.datauser()
        await this.listpost()
        this.loadings = false
      },

      onRowSelected(items: never[]) {
        this.selected = items
      },

      async datauser() {
        this.loadings = true
        const ip = await this.$axios.$get('users')
        this.items = ip
        this.loadings = false
      },

      rowClass(item: { status: string }, type: string) {
        if (!item || type !== 'row') return
        if (item.status === 'active') return 'table-success'
        if (item.status === 'inactive') return 'table-danger'
      },

      info(item: any, index: any, button: any) {
        this.isnew = false
        this.infoModal.title = `Lihat Pengguna ( ${item.name} )`
        this.form.id = item.id
        this.form.email = item.email
        this.form.name = item.name
        this.form.gender = item.gender
        this.form.status = item.status
        this.posts.user_id = item.id
        this.$root.$emit('bv::show::modal', this.infoModal.id, button)
        this.listpost()
      },
      resetInfoModal() {
        this.infoModal.title = ''
        this.infoModal.content = ''
      },

      async onSubmit(event: { preventDefault: () => void }) {
        event.preventDefault()
        let submit = this.isnew ? await this.$axios.post('users', this.form) : await this.$axios.put(`users/${this.form.id}`, this.form)
        if(submit){
          this.alerts = 'success'
          this.alerts_message = 'success'
          this.modal_alert = true
        }else{
          this.alerts = 'danger'
          this.alerts_message = `Failed`
          this.modal_alert = true
        }
        this.modalnewuser = false;
        this.$root.$emit('bv::hide::modal', this.infoModal.id)
        this.datauser()
      },

      async onSubmitPost(event: { preventDefault: () => void }) {
        event.preventDefault()
        let submit = await this.$axios.post(`users/${this.form.id}/posts`, this.posts)
        if(submit){
          this.alerts = 'success'
          this.alerts_message = 'success'
          this.modal_alert = true
        }else{
          this.alerts = 'danger'
          this.alerts_message = `Failed`
          this.modal_alert = true
        }
        this.modalnewuser = false;
        this.$root.$emit('bv::hide::modal', this.postModal)
        this.listpost()
      },

      onReset() {
        this.form.id = null
        this.form.email = null
        this.form.name = null
        this.form.gender = null
        this.form.status = null
      }
    },

    async mounted() {
      await this.$axios.setHeader('Authorization','Bearer 9690fb8196780608aa119e9cadbf3901b8d6679995f2667a259a1f07fb7617cd')
      await this.datauser()
    },

    computed: {
      rows() {
        return this.items.length
      }
    }
  })
</script>
