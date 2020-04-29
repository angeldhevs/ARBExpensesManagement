<template>
<div class="sidenav">
    <div class="profile-box">
        <span>{{ auth.name }}({{ rolename }})</span>
    </div>
    <hr>
    <ul>
        <li>
            <a href="/account">Account</a>
        </li>
        <hr>
        <li>
        <a href="/dashboard">Dashboard</a>
        </li>
        <hr>
        <li v-if="auth.role_id == 1">
            <a href="#">User Management</a>
            <ul>
                <li><a href="/role">Roles</a></li>
                <li><a href="/user">Users</a></li>
            </ul>
        </li>
        <hr>
        <li>
            <a href="#">Expense Management</a>
            <ul>
                <li  v-if="auth.role_id == 1"><a href="/expensecategory">Expense categories</a></li>
                <li><a href="/expense">Expenses</a></li>
            </ul>
        </li>
    </ul>
</div>
</template>

<script>
    import { Request, Validate } from '../../utils/common';
    
    export default {
         mounted() {
            console.log('Sidebar mounted.')
        },
        props: {
            user: String,
            auth: Object,
            rolename: String
        },
        data() {
            return {

            }
        },
        methods: {

        }
    }
</script>
