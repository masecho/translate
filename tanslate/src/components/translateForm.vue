<template>
  <div class="row">
    <div class="col-md-6 col-md-offset-3 col-xs-10 col-xs-offset-1 col-sm-8 col-sm-offset-2">
      <form class="well form-inline border-form" v-on:submit="formSubmit">
        <input class="form-control" type="text" placeholder="输入翻译内容" v-model="toTranslateText">
        <select class="form-control trans-select" v-model="lang">
          <option value="en" >English</option>
          <option value="de">German</option>
          <option value="pt">Portuguese</option>
          <option value="ru">Russian</option>
          <option value="ja">Japanese</option>
          <option value="ko">Korean</option>
        </select>
        <button class="btn btn-primary" type="submit">翻译</button>
      </form>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'translateForm',
    data () {
      return {
        toTranslateText:"",
        lang:"en"
      }
    },
    methods:{
      formSubmit:function(e){
        if(!this.toTranslateText || !this.lang){
          return;
        }
        this.$emit("formSubmit1",this.toTranslateText,this.lang);
        e.preventDefault();
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
  .border-form{
    border: 1px  solid #ccc;
    border-radius:10px;
  }
  .trans-select{
    padding-left: 6px;
  }
</style>
