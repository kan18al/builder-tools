<template>
  <div class="sidebar-page">
    <section class="sidebar-layout">
      <b-sidebar
          :fullheight="true"
          position="static"
          :mobile="mobile"
          :expand-on-hover="true"
          :reduce="true"
          type="is-light"
          open
      >
        <div class="p-1">
          <div class="block">
            <img
                src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
                alt="Lightweight UI components for Vue.js based on Bulma"
            />
          </div>
          <b-menu class="is-custom-mobile">
            <b-menu-list label="Menu">
              <b-menu-item icon="information-outline" label="Info"></b-menu-item>
              <b-menu-item active expanded icon="settings" label="Administrator">
                <b-menu-item icon="account" label="Users"></b-menu-item>
                <b-menu-item icon="cellphone-link" label="Devices"></b-menu-item>
                <b-menu-item icon="cash-multiple" label="Payments" disabled></b-menu-item>
              </b-menu-item>
              <b-menu-item icon="account" label="My Account">
                <b-menu-item icon="account-box" label="Account data"></b-menu-item>
                <b-menu-item icon="home-account" label="Addresses"></b-menu-item>
              </b-menu-item>
            </b-menu-list>
            <b-menu-list>
              <b-menu-item label="Expo" icon="link"></b-menu-item>
            </b-menu-list>
            <b-menu-list label="Actions">
              <b-menu-item icon="logout" label="Logout"></b-menu-item>
            </b-menu-list>
          </b-menu>
        </div>
      </b-sidebar>

      <div class="p-1">
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    name: "SidebarUser",
    data() {
      return {
        expandOnHover: false,
        mobile: "reduce",
        reduce: false
      };
    },
    mounted() {
      console.log(this)
    }
  };
</script>

<style lang="scss">
  .p-1 {
    padding: 1em;
  }
  .sidebar-page {
    display: flex;
    flex-direction: column;
    width: 100%;
    min-height: 100%;
    // min-height: 100vh;
    .sidebar-layout {
      display: flex;
      flex-direction: row;
      min-height: 100%;
      // min-height: 100vh;
    }
  }
  @media screen and (max-width: 1023px) {
    .b-sidebar {
      .sidebar-content {
        &.is-mini-mobile {
          &:not(.is-mini-expand),
          &.is-mini-expand:not(:hover) {
            .menu-list {
              li {
                a {
                  span:nth-child(2) {
                    display: none;
                  }
                }
                ul {
                  padding-left: 0;
                  li {
                    a {
                      display: inline-block;
                    }
                  }
                }
              }
            }
            .menu-label:not(:last-child) {
              margin-bottom: 0;
            }
          }
        }
      }
    }
  }
  @media screen and (min-width: 1024px) {
    .b-sidebar {
      .sidebar-content {
        &.is-mini {
          &:not(.is-mini-expand),
          &.is-mini-expand:not(:hover) {
            .menu-list {
              li {
                a {
                  span:nth-child(2) {
                    display: none;
                  }
                }
                ul {
                  padding-left: 0;
                  li {
                    a {
                      display: inline-block;
                    }
                  }
                }
              }
            }
            .menu-label:not(:last-child) {
              margin-bottom: 0;
            }
          }
        }
      }
    }
  }
</style>
