<script setup>
import IconAvatarDefault from '@/components/icons/IconAvatarDefault.vue'
import IconBell from '@/components/icons/IconBell.vue'
import IconSearch from '@/components/icons/IconSearch.vue'
import IconWrite from '@/components/icons/IconWrite.vue'
</script>
<template>
    <header class="header flex justify-between items-center">
        <div class="header-left flex">
            <RouterLink to="/">
                <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="40" height="40" />
            </RouterLink>
            <div class="search-box flex items-center">
                <div class="search-icon-box">
                    <IconSearch class="search-icon" />
                </div>
                <input type="text" class="search-input" placeholder="search">
            </div>
        </div>

        <div class="header-right flex items-center">
            <IconSearch class="search-icon-mobile" />
            <div class="write-box">
                <IconWrite />
                <span class="write-text">Write</span>
            </div>
            <IconBell />
            <IconAvatarDefault />
        </div>
        <!-- <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div> -->
    </header>
</template>

<style lang="scss" scoped>
.header {
    height: 57px;
    border-bottom: solid 1px $color-tertiary;
    // position: fixed;
    // left: 0;
    // right: 0;
    // top: 0;

    .search-box {
        display: none;
    }

    .header-right {
        gap: 32px;

        .write-box {
            display: none;
        }
    }
}

@media screen and (min-width: 768px) {
    .header {
        .search-box {
            display: flex;
            position: relative;
            border-radius: 15px;
            background: #F9F9F9;
            width: 240px;
            height: 40px;
            margin-left: 16px;

            .search-icon-box {
                width: 24px;
                height: 24px;
                margin: 0 12px;
            }

            .search-input {
                width: 100%;
                padding: 10px 20px 10px 0;
                border: none;
                background: transparent;
                outline: none;
            }
        }

        .search-icon-mobile {
            display: none;
        }

        .header-right {
            .write-box {
                display: flex;
                gap: 8px;
                line-height: 2.4rem;
            }
        }
    }
}
</style>