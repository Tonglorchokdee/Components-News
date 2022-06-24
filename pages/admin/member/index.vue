<template>
    <v-row justify="center" class="mt-10">
        <v-col cols="12" sm="12" md="12" lg="12">
            <div class="border-bottom mb-6">
                <v-btn to="member/create" color="primary" class="btn-primary" large dark v-bind="attrs" v-on="on">
                    <v-icon>mdi-plus</v-icon> เพิ่มสมาชิก
                </v-btn>
                <v-btn color="#206C41" class="btn-primary ml-4" large dark v-bind="attrs" v-on="on">
                    <v-icon>mdi-file-excel</v-icon> import excel
                </v-btn>
            </div>

            <v-card>
                <v-card-title class="headline"> จัดการสมาชิก</v-card-title>
                <v-card-text>
                    <v-simple-table class="table-main">
                        <template v-slot:default>
                            <thead>
                                <tr>
                                    <th class="text-center">ลำดับ</th>
                                    <th class="text-left">เลขบัตรประจำตัวประชาชน</th>
                                    <th class="text-left">คำนำ</th>
                                    <th class="text-center">ชื่อ</th>
                                    <th class="text-center">สกุล</th>
                                    <th class="text-center">ประเภทบุคคล</th>
                                    <th class="text-center">เบอร์โทร</th>
                                    <th class="text-center">ตำแหน่ง</th>
                                    <th class="text-center">ฝ่าย</th>
                                    <th class="text-center">อีเมล</th>
                                    <th class="text-center">จัดการ</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="(item, i) in usermember" :key="item.name">
                                    <td class="text-center">{{ i + 1 }}</td>
                                    <td>1450700231841</td>
                                    <td>นาย</td>
                                    <td>ประหยัด</td>
                                    <td>คงดี</td>
                                    <td>หมอ</td>
                                    <td></td>
                                    <td></td>
                                    <td></td>
                                    <td>email@gmail.com</td>
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
    name: "user permissino ",
    layout: "dashboard",
    data: function () {
        return {
            loading: true,

            usermember: [
                {
                    name: "",

                }
            ],

        };
    },
};
</script>

