
<template>
  <div class="home">
    <div class="center">
      <button @click="clearText" class="button">Click here to clear the Editor</button>
    </div>
    <div class="content">
      <textarea v-model="input" id="editor"></textarea>
      <div id="preview" v-html="viewMarkdown"></div>
    </div>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
// eslint-disable-next-line
//import HelloWorld from "@/components/HelloWorld.vue";
import url from "../assets/logo.png";
import Footer from "@/components/Footer.vue";

export default {
  // eslint-disable-next-line
  name: "home",
  components: {
    Footer
  },
  data() {
    return {
      input: `# Welcome to my Vue Markdown Previewer!
# This is a sub-heading
## This is a sub-heading
### And another sub-heading

here\'s some more markdown: 

code, \`<div></div>\`, between 2 backticks.

\`\`\`
// this is multi-line code:

function anotherExample(firstLine, lastLine) {
  if (firstLine == '\`\`\`' && lastLine == '\`\`\`') {
    return multiLineCode;
  }
}
\`\`\`
  
You can also make text **bold**
Or make text _italic_.
Or make text **_both!_**
you can ~~cross stuff out~~.

There's also [links](https://www.freecodecamp.com)

and block quotes:

> Block Quotes!

tables:

Wild Header | Crazy Header | Another Header?
------------ | ------------- | ------------- 
Your content can | be here, and it | can be here....
And here. | Okay. | I think we get it.

- More lists.
  - Some are bulleted.
     - With different indentation levels.
        - That look like this.


1. And there are numbererd lists too.
1. Use just 1s if you want! 
1. But the list goes on...
- Even if you use dashes or asterisks.
* And last but not least, let's not forget embedded images:

![Vue.js Image](${url})`
    };
  },
  computed: {
    viewMarkdown() {
      return marked(this.input);
    }
  },
  methods: {
    clearText() {
      return (this.input = "");
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
  margin: 0 auto;
}

textarea {
  width: 100%;
  height: 100%;
  border: 2px solid $Grey;
}
#preview {
  border: 2px solid $Grey;
}
.button::-moz-focus-inner {
  border: 0;
  padding: 0;
  border: 1px solid #Light-gray;
}
.center {
  margin: 50px auto;
  text-align: center;
}

.button {
  display: inline-block;
  *display: inline;
  zoom: 1;
  padding: 6px 20px;
  margin: 0;
  cursor: pointer;
  border: 1px solid #bbb;
  overflow: visible;
  font: bold 13px arial, helvetica, sans-serif;
  text-decoration: none;
  white-space: nowrap;
  color: #555;

  background-color: #ddd;
  background-image: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(rgba(255, 255, 255, 1)),
    to(rgba(255, 255, 255, 0))
  );
  background-image: -webkit-linear-gradient(
    top,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0)
  );
  background-image: -moz-linear-gradient(
    top,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0)
  );
  background-image: -ms-linear-gradient(
    top,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0)
  );
  background-image: -o-linear-gradient(
    top,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0)
  );
  background-image: linear-gradient(
    top,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0)
  );

  -webkit-transition: background-color 0.2s ease-out;
  -moz-transition: background-color 0.2s ease-out;
  -ms-transition: background-color 0.2s ease-out;
  -o-transition: background-color 0.2s ease-out;
  transition: background-color 0.2s ease-out;
  background-clip: padding-box; /* Fix bleeding */
  -moz-border-radius: 3px;
  -webkit-border-radius: 3px;
  border-radius: 3px;
  -moz-box-shadow: 0 1px 0 rgba(0, 0, 0, 0.3), 0 2px 2px -1px rgba(0, 0, 0, 0.5),
    0 1px 0 rgba(255, 255, 255, 0.3) inset;
  -webkit-box-shadow: 0 1px 0 rgba(0, 0, 0, 0.3),
    0 2px 2px -1px rgba(0, 0, 0, 0.5), 0 1px 0 rgba(255, 255, 255, 0.3) inset;
  box-shadow: 0 1px 0 rgba(0, 0, 0, 0.3), 0 2px 2px -1px rgba(0, 0, 0, 0.5),
    0 1px 0 rgba(255, 255, 255, 0.3) inset;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.9);

  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.button:hover {
  background-color: #eee;
  color: #555;
}

.button:active {
  background: #e9e9e9;
  position: relative;
  top: 1px;
  text-shadow: none;
  -moz-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.3) inset;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.3) inset;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.3) inset;
}
@media (max-width: 600px) {
  .content {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
