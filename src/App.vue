<!-- 화면의 요소는 template안에 작업 -->
<template>
    <!-- vuetify에서는 모든 태그의 최상단에 v-app -->
    <v-app>
        <HeaderComponent/>
        <v-main>
        <!-- route-view는 현재 url에 매칭된 컴포넌트를 렌더링(화면 생성)하는 영역 -->
        <router-view/>
        </v-main>
        <FooterComponent/>
    </v-app>
</template>


<!-- js의 요소는 scrpint안에 작업 -->
<script>
import FooterComponent from './components/FooterComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';


// vue는 export를 통하여 .vue, .js등의 요소를 다른 화면에서도 import할 수 있도록 설정.
export default {
    // name을 생략시 파일명이 name이 됨.
    components: {
        HeaderComponent, 
        FooterComponent
    },
    name:"App"
}
</script>

<!-- css의 요소는 style안에 작업 -->
<style> 

</style>
