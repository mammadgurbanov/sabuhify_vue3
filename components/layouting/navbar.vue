<template>
    <v-app-bar
            image="https://plus.unsplash.com/premium_photo-1664036937348-d580c8d4b612?q=80&w=1982&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            scroll-behavior="fade-image"
            scroll-threshold="1000"

    >
        <v-container>


            <div class=" w-100 d-flex justify-space-between align-items-center">

                <div class="header-logo">
                    <img
                            src="/images/logo-placeholder.png"
                    />
                </div>

                <div class="d-flex align-center">
                    <v-btn
                            class="mx-1"
                            color="#5865f2"
                            prepend-icon="mdi-test-tube"
                            variant="flat"
                    >
                        Try demo
                    </v-btn>
                    <v-btn
                            class="mx-1"
                            color="#5865f2"
                            prepend-icon="mdi-login"
                            variant="flat"
                    >
                        Login
                    </v-btn>
                </div>
            </div>
        </v-container>
    </v-app-bar>
</template>

<script>
export default {}
</script>

<style lang="scss">
.test-logo {
  color: #fff;
  font-weight: bold;
  font-size: 30px;
  font-style: oblique;
}

.header-logo {
  width: 200px;
  height: auto;

  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    object-position: left;
  }
}
</style>
