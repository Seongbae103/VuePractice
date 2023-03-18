<template>

    <div class="white-bg">
        <h4>상세페이지</h4>
        <p>{{room[j].content}}</p>
        <button @click="modalChange(j)">x</button>
        <button @click="ben(j)">허위매물 신고</button> <span>신고수 : {{count[j]}}</span>
    </div>


</template>

<script>
export default {
    name: "InfoModal",
    data(){
        return{
            count: [0, 0, 0, 0, 0, 0],
        }
    },
    methods: {
        ben(i){
            this.count[i] +=1;
        },
        modalChange(i){
            if (this.modal[i] == false){
                this.modal[i] = true;
            }else{
                this.modal[i] = false;
            }
        }
    }
}
</script>

<style>

</style>