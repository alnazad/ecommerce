<script>
import axios from 'axios';
import { mapActions, mapGetters } from 'vuex'
export default {
  name: "CustomerPanel",
  data() {
    return {
      activeTab: 'orders',

    };
  },
  methods: {
    ...mapActions({
      logOut: 'auth/logout'
    }),
    setActiveTab(tab) {
      this.activeTab = tab;
    },
  },
  computed: {
    ...mapGetters('auth', {
      user: 'user',
    }),
  }
}
</script>

<template>
  <div>
    <div class="container">
      <div class="main-body">

        <!-- Breadcrumb -->
        <nav aria-label="breadcrumb" class="main-breadcrumb">
          <ol class="breadcrumb">
            <li class="breadcrumb-item"><a href="index.html">Home</a></li>
            <li class="breadcrumb-item"><a href="javascript:void(0)">User</a></li>
            <li class="breadcrumb-item active" aria-current="page">Customer</li>
          </ol>
        </nav>
        <!-- /Breadcrumb -->

        <div class="row gutters-sm">
          <div class="col-md-4 mb-3">
            <div class="card">
              <div class="card-body">
                <div class="d-flex flex-column align-items-center text-center">
                  <img :src="`http://127.0.0.1:8000/photos/users/${user.photo ? user.photo.path : 'no-image.jpg'}`" alt="Admin" class="rounded-circle"
                    width="150">
                  <div class="mt-3">
                    <h4>{{ user.name }}</h4>
                    <p class="text-secondary mb-1">Customer Account</p>
                    <button class="btn btn-primary mr-2">Follow</button>
                    <button class="btn btn-outline-primary">Message</button>
                    <button @click="logOut" class="btn btn-info ml-2">LogOut</button>
                  </div>
                </div>
              </div>
            </div>
            <div class="card mt-3">
              <ul class="list-group list-group-flush">
                <li class="list-group-item d-flex justify-content-between align-items-center flex-wrap">
                  <h6 class="mb-0"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                      fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                      class="feather feather-globe mr-2 icon-inline">
                      <circle cx="12" cy="12" r="10"></circle>
                      <line x1="2" y1="12" x2="22" y2="12"></line>
                      <path
                        d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z">
                      </path>
                    </svg>Website</h6>
                  <span class="text-secondary">https://bootdey.com</span>
                </li>
                <li class="list-group-item d-flex justify-content-between align-items-center flex-wrap">
                  <h6 class="mb-0"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                      fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                      class="feather feather-github mr-2 icon-inline">
                      <path
                        d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22">
                      </path>
                    </svg>Github</h6>
                  <span class="text-secondary">bootdey</span>
                </li>
                <li class="list-group-item d-flex justify-content-between align-items-center flex-wrap">
                  <h6 class="mb-0"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                      fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                      class="feather feather-twitter mr-2 icon-inline text-info">
                      <path
                        d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z">
                      </path>
                    </svg>Twitter</h6>
                  <span class="text-secondary">@bootdey</span>
                </li>
                <li class="list-group-item d-flex justify-content-between align-items-center flex-wrap">
                  <h6 class="mb-0"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                      fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                      class="feather feather-instagram mr-2 icon-inline text-danger">
                      <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
                      <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
                      <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
                    </svg>Instagram</h6>
                  <span class="text-secondary">bootdey</span>
                </li>
                <li class="list-group-item d-flex justify-content-between align-items-center flex-wrap">
                  <h6 class="mb-0"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                      fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                      class="feather feather-facebook mr-2 icon-inline text-primary">
                      <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
                    </svg>Facebook</h6>
                  <span class="text-secondary">bootdey</span>
                </li>
              </ul>
            </div>
          </div>
          <div class="col-md-8">
            <div class="card mb-3">
              <div class="card-body">
                <div class="row">
                  <div class="col-sm-3">
                    <h6 class="mb-0">Full Name</h6>
                  </div>
                  <div class="col-sm-9 text-secondary">
                    {{ user.name }}
                  </div>
                </div>
                <hr>
                <div class="row">
                  <div class="col-sm-3">
                    <h6 class="mb-0">Email</h6>
                  </div>
                  <div class="col-sm-9 text-secondary">
                    {{ user.email }}
                  </div>
                </div>
                <hr>
                <div class="row">
                  <div class="col-sm-3">
                    <h6 class="mb-0">Mobile</h6>
                  </div>
                  <div class="col-sm-9 text-secondary">
                    +88{{ user.phone_number }}
                  </div>
                </div>
                <hr>
                <div class="row">
                  <div class="col-sm-3">
                    <h6 class="mb-0">Address</h6>
                  </div>
                  <div class="col-sm-9 text-secondary">
                    {{ user.address }}
                  </div>
                </div>
                <hr>
                <div class="row">
                  <div class="col-sm-12">
                  </div>
                </div>
              </div>
            </div>

            <!-- navbar -->
            <div class="card mb-3 mt-3 mb-2">
              <div class="card-body">
                <div class="row">
                  <div class="nav-wrapper d-flex align-items-center justify-content-between ml-4">
                    <ul class="nav nav-pills d-none d-md-flex" id="pills-tab" role="tablist">
                      <li class="nav-item" role="presentation">
                        <router-link :to="{ name: 'customer-order-list' }" class="nav-link" id="pills-company-tab"
                          :class="{ active: activeTab === 'orders' }" @click.prevent="setActiveTab('orders')"
                          data-toggle="pill" href="#pills-company" role="tab" aria-controls="pills-company"
                          aria-selected="true">Orders</router-link>
                      </li>
                      <li class="nav-item" role="presentation">
                        <router-link :to="{ name: 'customer-wish-list' }" class="nav-link" id="pills-product-tab"
                          :class="{ active: activeTab === 'wishlist' }" @click.prevent="setActiveTab('wishlist')"
                          data-toggle="pill" href="#pills-product" role="tab" aria-controls="pills-product"
                          aria-selected="false">Wishlist</router-link>
                      </li>
                      <li class="nav-item" role="presentation">
                        <a class="nav-link" id="pills-news-tab" :class="{ active: activeTab === 'cart' }"
                          @click.prevent="setActiveTab('cart')" data-toggle="pill" href="#pills-news" role="tab"
                          aria-controls="pills-news" aria-selected="false">Cart</a>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
            <!-- navbar end -->

            <div class="row gutters-sm">
              <div class="col-sm-12 mb-3">
                <div class="card h-100">
                  <div class="card-body">
                    <router-view />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
body {
  margin-top: 20px;
  color: #1a202c;
  text-align: left;
  background-color: #e2e8f0;
}

.main-body {
  padding: 15px;
}

.card {
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, .1), 0 1px 2px 0 rgba(0, 0, 0, .06);
}

.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: #fff;
  background-clip: border-box;
  border: 0 solid rgba(0, 0, 0, .125);
  border-radius: .25rem;
}

.card-body {
  flex: 1 1 auto;
  min-height: 1px;
  padding: 1rem;
}

.gutters-sm {
  margin-right: -8px;
  margin-left: -8px;
}

.gutters-sm>.col,
.gutters-sm>[class*=col-] {
  padding-right: 8px;
  padding-left: 8px;
}

.mb-3,
.my-3 {
  margin-bottom: 1rem !important;
}

.bg-gray-300 {
  background-color: #e2e8f0;
}

.h-100 {
  height: 100% !important;
}

.shadow-none {
  box-shadow: none !important;
}
</style>