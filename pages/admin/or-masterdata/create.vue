<template>
    <v-row justify="center" class="mt-10">
        <v-col cols="12" sm="12" md="12">
            <v-card>
                <v-card-title class="headline pl-10 pt-10">
                    เพิ่มห้องผ่าตัด
                </v-card-title>
                <v-card-text>
                    <v-container id="input-usage" fluid>
                        <v-row class="form-row">
                            <v-col cols="7" offset-md="3">
                                <v-alert border="left" color="red" dense dismissible outlined type="info">ค่าที่มี *
                                    จำเป็นต้องใส่ให้ครบ</v-alert>
                            </v-col>
                        </v-row>
                        <v-row class="form-row">
                            <v-col cols="3" class="text-right">
                                <label class="label-main"> ชื่อห้อง<span class="text-danger">*</span></label>
                            </v-col>
                            <v-col cols="7">
                                <v-text-field outlined></v-text-field>
                            </v-col>
                        </v-row>

                        <v-row class="form-row">
                            <v-col cols="3" class="text-right">
                                <label class="label-main"> ชื่ออาคาร<span class="text-danger">*</span></label>
                            </v-col>
                            <v-col cols="7">
                                <v-text-field outlined></v-text-field>
                            </v-col>
                        </v-row>


                        <v-row class="form-row">
                            <v-col cols="3" class="text-right">
                                <label class="label-main"> สถานะแสดงผล</label>
                            </v-col>
                            <v-col cols="7">
                                <v-switch class="mt-0" v-model="switch1"></v-switch>
                            </v-col>
                        </v-row>

                        <v-row class="form-row row-btn">
                            <v-col cols="9" offset-md="3">
                                <v-btn color="primary" large class="mx-2 btn-primary" elevation="2">
                                    <v-icon>mdi-check</v-icon>บันทึกข้อมูล
                                </v-btn>
                                <GoBack></GoBack>
                            </v-col>
                        </v-row>


                    </v-container>
                </v-card-text>

            </v-card>
        </v-col>
    </v-row>
</template>

<script>
import moment from 'moment'
export default {
    auth: true,
    name: "Mainmenu",
    layout: "dashboard",
    data: function () {
        return {
            loading: true,
            show1: false,
            show2: false,
            password: '',
            rules: {
                required: value => !!value || 'จำเป็นต้องกรอก',
                min: v => v.length >= 8 || 'ขั้นต่ำ 8 ตัวอักษร',
                emailMatch: () => (`The email and password you entered don't match`),
            },
            items: ['ผู้ใช้งานทั่วไป', 'เจ้าหน้าที่'],
            items2: ['หมอ', 'พยาบาล', 'ผู้ดูแลประจำห้องผ่าตัด'],
        }
    },


};
</script>

