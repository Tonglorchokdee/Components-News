<template>
    <v-row justify="center" class="mt-10">
        <v-col cols="12" sm="12" md="12" lg="12">
            <div class="border-bottom mb-6">
                <v-btn to="or-masterdata/create" color="primary" class="btn-primary" large dark v-bind="attrs" v-on="on">
                    <v-icon>mdi-plus</v-icon> เพิ่มห้องผ่าตัด
                </v-btn>
            </div>

            <v-card>
                <v-card-title class="headline"> จัดการห้องผ่าตัด</v-card-title>
                <v-card-text>
                    <v-simple-table class="table-main">
                        <template v-slot:default>
                            <thead>
                                <tr>
                                    <th class="text-center">ลำดับ</th>
                                    <th class="text-left">ชื่อห้อง</th>
                                    <th class="text-left">ชื่ออาคาร</th>
                                    <th class="text-center">สถานะแสดงผล</th>
                                    <th class="text-center">จัดการ</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="(item, i) in orroom" :key="item.name">
                                    <td class="text-center">{{ i + 1 }}</td>
                                    <td></td>
                                    <td></td>
                                    <td>
                                        <v-row justify="center">
                                            <v-switch v-model="switch1"></v-switch>
                                        </v-row>
                                    </td>
                                    <td class="text-center">
                                        <v-btn color="secondary" icon elevation="0" small>
                                            <v-icon>mdi-pen</v-icon>
                                        </v-btn>
                                        <v-btn color="error" icon elevation="0" small>
                                            <v-icon>mdi-delete</v-icon>
                                        </v-btn>
                                    </td>
                                </tr>
                            </tbody>
                        </template>
                    </v-simple-table>
                </v-card-text>
            </v-card>
        </v-col>
    </v-row>
</template>

<script>
export default {
    auth: true,
    name: "or room ",
    layout: "dashboard",
    data: function () {
        return {
            loading: true,
            orroom: [
                {
                    name: "",

                }
            ],

        };
    },
};
</script>

