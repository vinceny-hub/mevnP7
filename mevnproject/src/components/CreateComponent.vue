<template>
 <div class="container pb-cmnt-container">
    <div class="row">
        <div class="col-md-6 offset-md-3">
            <div class="card card-info">
                <div class="card-block">

                   
  <h1 class="mt-2 text-center">Create a post</h1>
   
           
  <form @submit.prevent="addPost">
  
   <div >
    <div >
     <div class="">
      <!-- <label>Post Title:</label> -->
      <input  class="container mt-2 text-center"  placeholder=" Give a title to your post !" type=text v-model="post.title">
     </div>
    </div>
    </div>
    <div >
     <div >
      <div class="mt-4 border border-dark">
       <!-- <label>Post Body:</label> -->
       
       <textarea class="pb-cmnt-textarea" placeholder="Write your comment here!" v-model="post.body" rows="5"></textarea>
      
      </div>
     </div>
    </div><br />
    <div class="text-center" >
     <button class="btn btn-primary">Share</button>
    </div>
  </form>
                </div></div></div></div>
      
 </div>
</template>

<script>
  export default {
    data(){
    return {
     post:{}
    }
  },
  methods: {
 addPost(){
    let uri = '//localhost:3300/posts/add';
    this.axios.post(uri, this.post).then(() => {
       this.$router.push({name: 'posts'});
    });
}
 }}
</script>

<style>
    .pb-cmnt-container {
        font-family: Lato;
        margin-top: 100px;
    }

    .pb-cmnt-textarea {
        resize: none;
        padding: 20px;
        height: 130px;
        width: 100%;
        border: 1px solid #F2F2F2;
    }

 
</style>
