<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container class="my-5">
      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
            <div>{{ project.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{ project.due }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="right">
              <v-chip
                small
                :class="`${project.status} white--text caption my-2`"
              >{{ project.status }}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
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
          person: "Sulay Sumaria",
          due: "10th Jan 2019",
          status: "complete",
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Laborum reprehenderit laboriosam molestiae fuga vero voluptatem, recusandae, rem minus corrupti sunt pariatur explicabo inventore magnam maiores perspiciatis! Fugiat earum quam mollitia!"
        },
        {
          title: "Design video thumbnails",
          person: "Sulay Sumaria",
          due: "20th Dec 2018",
          status: "complete",
          content:
            "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Unde, deserunt. Recusandae fugiat rem quas? Aperiam, praesentium perferendis voluptatem animi culpa ipsum atque mollitia dicta fugiat ipsa non sit itaque cumque!"
        },
        {
          title: "Create a community forum",
          person: "Sulay Sumaria",
          due: "20th Oct 2018",
          status: "overdue",
          content:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Iste repellat voluptatem asperiores reprehenderit accusantium quo natus cum earum pariatur quae omnis, ex rerum, a at qui excepturi? Expedita, minima ipsam."
        }
      ]
    };
  }
};
</script>

<style scoped>
.project.complete {
  border-left: 4px solid #3cd1c2;
}

.project.ongoing {
  border-left: 4px solid orange;
}

.project.overdue {
  border-left: 4px solid tomato;
}

.v-chip.complete {
  background: #3cd1c2;
}

.v-chip.ongoing {
  background: #ffaa2c;
}

.v-chip.overdue {
  background: #f83e70;
}
</style>
