<template>
  <div>
    <div class="">
      <nav 
        class="navbar navbar-expand-md navbar-light navbar-btn-box "
      >
        <button 
          class="navbar-toggler navbar-toggler-right header_navbar_member" 
          type="button" 
          data-toggle="collapse" 
          data-target="#header_navbar" 
          aria-controls="header_navbar" 
          aria-expanded="false" 
          aria-label="Toggle navigation"> 
          <span class="navbar-toggler-icon"></span> 
        </button>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MobileNav'
}
</script>

<style lang="scss">
  .navbar-btn-box {
    display: flex;
    flex-direction: row;
    align-items: center;
  }
</style>