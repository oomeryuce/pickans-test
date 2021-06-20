<template>
  <main>
    <page-base>
      <Feed :items="feedItems" />
    </page-base>
  </main>
</template>

<script>
import PageBase from "../components/PageBase";
import Feed from "../components/Feed";
export default {
  components: { PageBase, Feed },
  data() {
    return {
      feedItems: [
        {
          id: 1,
          author: "Sencer SOYLU",
          authorTitle: "CTO of Pickans",
          type: "Category",
          title: "Hosting your own password management instance",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at cumque ducimus enim eum excepturi iste maiores, nemo neque numquam obcaecati provident quidem quo quod veniam! Iste magnam repellendus reprehenderit.",
          date: "2h ago",
          likes: 3,
        },
        {
          id: 2,
          author: "Sencer SOYLU",
          authorTitle: "CTO of Pickans",
          type: "Category",
          title: "Hosting your own password management instance",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at cumque ducimus enim eum excepturi iste maiores, nemo neque numquam obcaecati provident quidem quo quod veniam! Iste magnam repellendus reprehenderit.",
          date: "2h ago",
          likes: 3,
        },
        {
          id: 3,
          author: "Sencer SOYLU",
          authorTitle: "CTO of Pickans",
          type: "Category",
          title: "Hosting your own password management instance",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at cumque ducimus enim eum excepturi iste maiores, nemo neque numquam obcaecati provident quidem quo quod veniam! Iste magnam repellendus reprehenderit.",
          date: "2h ago",
          likes: 3,
        },
        {
          id: 4,
          author: "Sencer SOYLU",
          authorTitle: "CTO of Pickans",
          type: "Category",
          title: "Hosting your own password management instance",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at cumque ducimus enim eum excepturi iste maiores, nemo neque numquam obcaecati provident quidem quo quod veniam! Iste magnam repellendus reprehenderit.",
          date: "2h ago",
          likes: 3,
        }
      ]
    }
  }
}
</script>

<style></style>
