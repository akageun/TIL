# Nuxt, Pages API

```vue
<template>
    <div>

    </div>
</template>
<script>
    export default {

        /**
         * vue 인스턴스가 생성되기 전 store 초기화
         * - data()나 asyncData 처럼 데이터를 가지고 오는건 같음.(초기화하는 대상이 다름)
         * - data()나 asyncData 는 컴포넌트에서 사용하는 데이터 초기화.
         * - fetch는 vuex인 데이터 store에 데이터를 초기화 하기 위해 사용.
         *
         * @param store : vuex의 store와 같은 저장소
         * @param params
         */
        fetch({store, params}) {
            const mockData = {
                test: 'Temp Value'
            };

            store.commit('update', mockData);
        },

        /**
         * 인스턴스가 생성될 때 호출
         */
        created() {

        },

        /**
         * 비동기로 데이터를 호출, Json 형태로 반환되며 data()와 merge 됨.
         * - data() 와 동일하게 사용하면됨.
         * - vuex가 설정되어 있을 경우 store를 사용할 수 있음.
         * - env를 이용하면 config에 설정된 환경변수도 사용 가능.
         *
         * @param context : url에 있는 params나 query 등을 가지고 올 수 있다.
         * @returns {{}}
         */
        asyncData(context) {
            return {}
        },

        /**
         * 데이터 생성
         *
         * @returns {}
         */
        data() {
            return {}
        },

        /**
         * 해당 페이지의 <head> 영역 커스텀할 수 있는 영역.
         *
         * @returns {}
         */
        head() {
            return {
                title: '',
                meta: {
                    hid: '고유값',
                    name: 'description',
                    content: 'Custom Description'
                }
            }
        },

        /**
         * 해당 파일에서 동작시킬 메소드 정의
         */
        methods: {},

        /**
         * 복잡한 계산식일 경우 사용되는 영역
         */
        computed: {},

        /**
         * 외부 컴포넌트 추가 {a, b, c} 형태로 작성
         *  - import a from '~/components/a'
         */
        components: {},

        /**
         * layout 관련된 설정
         *  - 미 작성시 default 로 사용됨.
         *  - layout: '' 형태로도 사용 가능
         *
         * @param context
         * @returns {string}
         */
        layout(context) {
            return 'customLayout'
        },

        /**
         * 미들웨어 설정
         */
        middleware: '',

        /**
         * 페이지의 스크롤 상단/하단 여부
         * 최상단 : true, 최하단 false
         */
        scrollToTop: true || false
    }

</script>
<!--
 scoped는 해당 vue 파일에만 style옵션을 넣겠다는 옵션
-->
<style scoped>

</style>

```