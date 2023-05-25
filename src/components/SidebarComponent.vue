<template>
    <div class="back" type="button" @click="toggleSidebar" :class="{ 'close': !sidebaropen, 'open': sidebaropen }">
        <img src="/assets/Vector.png" class="back-bracket" :class="{ 'close': !sidebaropen, 'open': sidebaropen }">
        <img src="/assets/back.png" class="back-arrow" :class="{ 'close': !sidebaropen, 'open': sidebaropen }">
    </div>

    <div class="sidebar-menu" :class="{ 'close': !sidebaropen, 'open': sidebaropen }">
        <div class="sidebar-header">
            <div class="logo">
                <img src="/assets/logo.png" alt="Logo" />
            </div>
            <div class="title-label">Serelo</div>
        </div>


        <ul>
            <li v-for="item in menuItems" :key="item.id">
                <a v-if="item.children" href="#" @click="toggleDropdown(item)">
                    <img :src="item.image" class="menu-item-image" />
                    <div class="item-label">
                        {{ item.label }}
                    </div>
                    <img src="/assets/dropdown.png" class="dropdown-icon" :class="{ 'open': item.open }">
                </a>
                <a v-else :href="item.link">
                    <img :src="item.image" class="menu-item-image" />
                    <div class="item-label">
                        {{ item.label }}
                    </div>
                </a>
                <ul v-if="item.children && item.open">
                    <li v-for="child in item.children" :key="child.id" style="margin-top: 10px;">
                        <a :href="child.link">
                            <span class="bullet-drop">&#x2022;</span>
                            <div class="item-label">
                                {{ child.label }}
                            </div>
                        </a>
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            menuItems: [
                { id: 1, label: 'Dashboard', image: '/assets/house.png', link: '/' },
                {
                    id: 2,
                    label: 'Data Master', image: '/assets/category.png',
                    children: [
                        { id: 21, label: 'Building', link: '/datamaster/building' },
                        { id: 22, label: 'Floor', link: '/datamaster/floor' },
                        { id: 23, label: 'Tenant', link: '/datamaster/tenant' },
                        { id: 24, label: 'Employee', link: '/datamaster/employee' },
                        { id: 25, label: 'Meeting Room', link: '/datamaster/meeting-room' },
                        { id: 26, label: 'Vehicle Questionnaire', link: '/datamaster/vechicle-questionnaire' },
                        { id: 26, label: 'Keys', link: '/datamaster/keys' },
                    ],
                },
                { id: 3, label: 'Visitor Reservation', image: '/assets/login.png', link: '/visitor-reservation' },
                { id: 4, label: 'Office Reservation', image: '/assets/buliding.png', link: '/office-reservation' },
                { id: 5, label: 'Desk Reservation', image: '/assets/Group 8.png', link: '/desk-reservation' },
                { id: 6, label: 'Meeting Room Reservation', image: '/assets/meeting.png', link: '/meeting-room-reservation' },
                { id: 7, label: 'Key Transactions', image: '/assets/task-square.png', link: '/key-transaction' },
                { id: 8, label: 'Vehicle Records', image: '/assets/group.png', link: '/vehicle-records' },
                { id: 9, label: 'Registration Approval', image: '/assets/task-square (1).png', link: '/registration-approval' },
                {
                    id: 10,
                    label: 'Reporting', image: '/assets/book.png',
                    children: [
                        { id: 101, label: 'Company', link: '/about/company' },
                        { id: 102, label: 'Team', link: '/about/team' },
                    ],
                },

            ],
            sidebaropen: true,
        };
    },
    methods: {
        toggleDropdown(item) {
            item.open = !item.open;
        },

        toggleSidebar() {
            const sidebar = this.sidebaropen;
            if (sidebar == true) {
                this.sidebaropen = false;
            } else if (sidebar == false) {
                this.sidebaropen = true;
            }

        }
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat');


.back-bracket {
    display: flex;
    position: absolute;
    left: 250px;
    top: 15px;
    transition: 0.3s ease;
}

.back-arrow {
    display: flex;
    position: absolute;
    left: 260px;
    top: 21px;
    transition: 0.3s ease;
}

.back-bracket.close {
    display: flex;
    position: absolute;
    left: 15px;
    top: 15px;
    transition: 0.3s ease;
}

.back-arrow.close {
    display: flex;
    position: absolute;
    transform: rotate(180deg);
    left: 25px;
    top: 21px;
    transition: 0.3s ease;
}

.sidebar-menu {
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    width: 15%;
    background-color: white;
    padding: 16px;
    overflow-y: auto;
    border: 1px solid #B6B6B6;
    transition: 0.3s ease;
}

.sidebar-menu.close {
    position: fixed;
    left: -250px;
}


.title-label {
    font-family: 'Montserrat';
    font-style: normal;
    font-weight: 900;
    font-size: 22px;
    line-height: 27px;
}

.menu-item-image {
    margin-right: 10px;
}

.bullet-drop {
    margin-right: 10px;
}



.sidebar-menu {
    -ms-overflow-style: none;
    /* Internet Explorer 10+ */
    scrollbar-width: none;
    /* Firefox */
}

.sidebar-menu::-webkit-scrollbar {
    display: none;
    /* Safari and Chrome */
}

.sidebar-header {
    align-items: left;
    margin-bottom: 16px;
    margin-top: 20px;
}

.logo {
    width: 37.12px;
    height: 22px;
    top: 45px;
}

.item-label {
    width: 71px;
    height: 27px;

    top: 67px;

    font-family: 'Montserrat';
    font-style: normal;
    font-weight: 700;
    font-size: 13px;
    line-height: 27px;
}

.sidebar-menu ul li a {
    width: 150px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.sidebar-menu ul li a .label-item {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    font-family: 'Montserrat';
    font-style: normal;
    font-weight: bolder;
    font-size: 13px;
    line-height: 16px;
}

.sidebar-menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.sidebar-menu li {
    margin-bottom: 1.5rem;

}

.sidebar-menu a {
    color: #333;
    text-decoration: none;
    font-size: 16px;
    display: flex;
    align-items: center;
}

.dropdown-icon {
    margin-left: 15px;
}

.dropdown-icon.open {
    transform: rotate(180deg);
}

.sidebar-menu ul ul {
    margin-top: 8px;
    padding-left: 16px;
}
</style>
