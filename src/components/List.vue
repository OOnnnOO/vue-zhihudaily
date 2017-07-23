<template>
  <ul class="list">
    <li v-for="story in stories" class="list-item">
      <router-link :to="`detail/${story.id}`">
        <img v-bind:src="story.images[0]">
        <h2>{{story.title}}</h2>
      </router-link>
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'list',
    data() {
      return {
        stories: [
          // {title:'什么样算是有意义的生活?',
          // images:["https://pic4.zhimg.com/v2-18189a1c413d282e14185698d2dbf873.jpg"],
          // id:'9314977'},
          // {title:'什么22222样算是有意义的生活？',
          // images:["https://pic4.zhimg.com/v2-18189a1c413d282e14185698d2dbf873.jpg"],
          // id:'931429772222'}
        ]
      }
    },
    created: function () {
      this.$http.get("//zhihudaily.p.oonnnoo.com" + "/api/4/news/latest")
        .then(function (response) {
          this.stories = response.data.stories;
          // console.log(response.data)
        }, function (err) {
          console.log(err);
        });
    }
  }
</script>
<style>
  ul {
    list-style: none;
  }

  a {
    text-decoration: none;
  }

  a,
  a:visited {
    color: #2f2f2f
  }

  a:hover {
    text-decoration: underline;
  }

  .list {
    margin: 0 auto;
    list-style: none;
    width: 1240px;
  }

  .list-item {
    float: left;
    margin: 4px;
    padding: 8px 0 0;
    border: 1px solid #ccc;
    width: 300px;
    height: 220px;
  }

  .list-item h2 {
    font-size: 18px;
  }

  @media screen and (max-width:1240px) {
    .list {
      margin: 0 auto;
      list-style: none;
      width: 620px;
    }
  }

  @media screen and (max-width:620px) {
    .list {
      margin: 0 auto;
      list-style: none;
      width: 320px;
    }
  }

</style>
