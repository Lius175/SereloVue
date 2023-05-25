<template>
    <div class="header">
        <div class="profile">
            <img src="/assets/profile.png" class="profile-logo">
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            sidebaropen: true,
        }
    },

    methods: {
        toggleSidebar() {
            const sidebar = this.sidebaropen;
            if (sidebar == true) {
                this.sidebaropen = false;
            } else if (sidebar == false) {
                this.sidebaropen = true;
            }

        }
    }
};
</script>

<style>
.header {
    display: flex;
    align-items: center;
    justify-content: right;
    background-color: #f0f0f0;
    height: 50px;
    width: 100%;
    top: 0%;
    right: 0%;
    background: #FFFFFF;
    border: 1px solid #B6B6B6;
}





.profile {
    display: flex;
    align-items: right;
    margin-right: 15px;
    right: 0;
}

.profile img {
    align-items: right;
    width: 32px;
    height: 32px;
    border-radius: 50%;
    right: 8px;
}
</style>

