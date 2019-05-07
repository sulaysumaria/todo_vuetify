<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>
    <v-container class="my-5">
      <v-expansion-panel>
        <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
          <div slot="header">{{project.title}}</div>
          <v-card>
            <v-card-text class="px-4 grey--text">
              <div class="font-weight-bold">due by {{project.due}}</div>
              <div>{{project.content}}</div>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Design a new website",
          person: "Sulay Sumaria",
          due: "1st Jan 2019",
          status: "ongoing",
          content:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Accusamus suscipit iste iure, optio nulla esse, qui, quae ab consequatur eligendi aliquam rerum illum dignissimos similique minus. Dolorum cumque dignissimos eveniet?"
        },
        {
          title: "Code up the homepage",
          person: "Chun Li",
          due: "10th Jan 2019",
          status: "complete",
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Laborum reprehenderit laboriosam molestiae fuga vero voluptatem, recusandae, rem minus corrupti sunt pariatur explicabo inventore magnam maiores perspiciatis! Fugiat earum quam mollitia!"
        },
        {
          title: "Design video thumbnails",
          person: "Ryu",
          due: "20th Dec 2018",
          status: "complete",
          content:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde, deserunt. Recusandae fugiat rem quas? Aperiam, praesentium perferendis voluptatem animi culpa ipsum atque mollitia dicta fugiat ipsa non sit itaque cumque!"
        },
        {
          title: "Create a community forum",
          person: "Gouken",
          due: "20th Oct 2018",
          status: "overdue",
          content:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Iste repellat voluptatem asperiores reprehenderit accusantium quo natus cum earum pariatur quae omnis, ex rerum, a at qui excepturi? Expedita, minima ipsam."
        }
      ]
    };
  },
  computed: {
    myProjects() {
      return this.projects.filter(
        project => project.person === "Sulay Sumaria"
      );
    }
  }
};
</script>
