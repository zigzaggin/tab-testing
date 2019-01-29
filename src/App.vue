<template>
  <div id="app">
    <Page class="p" title="Page with 3 Tabs">
      <Tab name="Tab 1"> T1 Content </Tab> <Tab name="Tab 2"> T2 Content </Tab>
      <Tab name="Tab 3"> T3 Content </Tab>
    </Page>
    <Page class="p" title="Page with 2 Tabs">
      <Tab name="Tab 1"> T1 Content </Tab> <Tab name="Tab 2"> T2 Content</Tab>
    </Page>
    <Page class="p" title="Page with 1 Tab">
      <Tab name="Tab 1"> T1 Content </Tab>
    </Page>
    <Page class="p" title="Page without Tabs">
      <Test></Test> Also with some other text
    </Page>
  </div>
</template>

<script>
import Page from "./components/Page";
import Tab from "./components/Tab";
import Test from "./components/Test";

export default {
  name: "App",
  components: {
    Page,
    Tab,
    Test
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 800px;
  margin: 0px auto;
  padding: 10px;
}
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
.p {
  margin-top: 50px;
}
</style>
