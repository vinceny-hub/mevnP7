<template>
 <div>
   <h1>Posts</h1>
    <div >
     <div ></div>
     <div >
      <router-link :to="{ name: 'create' }" > <button class="btn btn-primary">Create a new post</button></router-link>
     </div>
    </div><br />

    <table >
      <thead>
      <tr>
       <th>Title</th>
       <th>Body</th>
       <th>Actions</th>
      </tr>
      </thead>
      <tbody>
        <tr v-for="post in posts" :key="post._id">
         <td>{{ post.title }}</td>
         <td>{{ post.body }}</td>
         <td><router-link :to="{name: 'edit', params: { id: post._id }}" >Edit</router-link></td>
         <td><button @click.prevent="deletePost(post._id)">Delete</button></td>
        </tr>
      </tbody>
    </table>
 </div>
</template>

<script>
 export default {
   data() {
    return {
     posts: []
    }
   },
   created() {
   let uri = '//localhost:3300/posts';
   this.axios.get(uri).then(response => {
    this.posts = response.data;
   });
  },
  methods: {
   deletePost(id)
   {
    let uri = `//localhost:3300/posts/delete/${id}`;
    this.axios.delete(uri).then(response => {
     this.posts.splice(this.posts.indexOf(id), 1);
     console.log(response)
    });
   }
  }
 }
</script>