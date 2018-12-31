
<template>
  <div class="home">
    <button @click="clearText">Click here to clear the Editor</button>
    <div class="content">
      <div class="one">
        <textarea v-model="input"></textarea>
      </div>
      <div class="two" id="preview" v-html="viewMarkdown"></div>
    </div>
    <!--<img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  </div>
</template>

<script>
// @ is an alias to /src
// eslint-disable-next-line
//import HelloWorld from "@/components/HelloWorld.vue";

export default {
  // eslint-disable-next-line
  name: "home",
  components: {
    // eslint-disable-next-line
    //HelloWorld
    // eslint-disable-next-line
  },
  data() {
    return {
      input: `# Welcome to my React Markdown Previewer!
## This is a sub-heading...
### And here\'s some other cool stuff: 

Heres some code, \`<div></div>\`, between 2 backticks.

\`\`\`
// this is multi-line code:

function anotherExample(firstLine, lastLine) {
  if (firstLine == '\`\`\`' && lastLine == '\`\`\`') {
    return multiLineCode;
  }
}
\`\`\`
  
You can also make text **bold**... whoa!
Or _italic_.
Or... wait for it... **_both!_**
And feel free to go crazy ~~crossing stuff out~~.

There's also [links](https://www.freecodecamp.com), and
> Block Quotes!

And if you want to get really crazy, even tables:

Wild Header | Crazy Header | Another Header?
------------ | ------------- | ------------- 
Your content can | be here, and it | can be here....
And here. | Okay. | I think we get it.

- And of course there are lists.
  - Some are bulleted.
     - With different indentation levels.
        - That look like this.


1. And there are numbererd lists too.
1. Use just 1s if you want! 
1. But the list goes on...
- Even if you use dashes or asterisks.
* And last but not least, let's not forget embedded images:

![Benjamin Bannekat](https://octodex.github.com/images/bannekat.png)`
    };
  },
  computed: {
    viewMarkdown() {
      return marked(this.input, { breaks: true, anchorTargetBlank: true });
    }
  }
};
</script>
<style scoped lang='scss'>
@import "../../public/styles.scss";

.content {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-auto-rows: minmax(200px, auto);
  max-width: 960px;
  grid-gap: 2px;
}
.one,
.two {
  border: 5px solid orangered;
}
textarea {
  width: 100%;
  height: 100%;
}
#preview {
}
</style>
