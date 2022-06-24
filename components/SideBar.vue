<template>
    <v-list>
        <template v-for="(menu, menui) in menus">
            <!-- Single Item -->
            <div>
                <v-list-item v-if="!menu.list" :key="menui" link :to="menu.to" router exact>
                    <v-list-item-icon class="mr-4">
                        <v-badge :content="menu.notificaition" :value="menu.notificaition" color="red" overlap>
                            <v-icon v-text="menu.icon" />
                        </v-badge>
                    </v-list-item-icon>
                    <v-badge class="mr-1" color="secondary" inline :content="menu.listnumber" :value="menu.listnumber">
                    </v-badge>
                    <v-list-item-title v-text="menu.title" />
                </v-list-item>
            </div>

            <!-- Multi Item -->
            <div>
                <v-list-group no-action v-if="menu.list" :key="menui">
                    <template v-slot:activator>
                        <v-icon slot="prependIcon" class="mr-4" v-text="menu.icon" />
                        <v-badge class="mr-1" color="secondary" inline :content="menu.listnumber"
                            :value="menu.listnumber">
                        </v-badge>
                        <v-list-item-title v-text="menu.title" />
                    </template>

                    <v-list-item v-for="(sub, subi) in menu.list" :key="subi" link :to="sub.to" router exact>
                        <v-list-item-title v-text="sub.label" />
                    </v-list-item>
                </v-list-group>
            </div>

        </template>
    </v-list>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    name: "sidebar",
    data() {
        // TODO: Implement routes here
        return {
            user: this.$auth.user,
            drawer: null,
            menus: [
                {
                    icon: "mdi-home",
                    title: "หน้าหลัก",
                    to: "/admin",
                    listnumber: "",
                    notificaition: "",
                },
                {
                    icon: "mdi-folder-home",
                    title: "จัดการห้องผ่าตัด",
                    to: "/admin/or-masterdata",
                    listnumber: "",
                    notificaition: "",
                },
                 {
                    icon: "mdi-account-group",
                    title: "จัดการสมาชิก",
                    to: "/admin/member",
                    listnumber: "",
                    notificaition: "",
                },


            ],
        };
    },
    methods: {
        doLogout: function () {
            this.$auth.logout().then(() => {
                this.redirect("/login");
            });
        },
        redirect: function (path: string) {
            setTimeout(() => this.$router.push(path), 300)
        }
    },
});
</script>

<style lang="scss" scoped>
</style>