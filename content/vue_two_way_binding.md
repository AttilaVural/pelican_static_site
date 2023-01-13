Title: Two-way binding in Vue.js
Date: 2019-10-20 11:20
Category: Python
Author: Attila Vural
Tags: pelican, tutorial



In this example, we have an input element and a paragraph element. The v-model directive is used to bind the value of the input element to a data property called message.

The message property is defined in the Vue instance's data object. The {{ message }} syntax in the paragraph element is a template expression that will be replaced with the value of the message property when the view is rendered.

So, when you load the example in a browser, you will see the text 'Hello World!' written in the paragraph, and when you type something into the input, the text written in the paragraph will change, reflecting the change you made in the input.

This is an example of two-way data binding because any changes made to the input element will be reflected in the message property and in turn, the paragraph element, and any changes made to the message property will be reflected in the input and the paragraph.

It's worth noting that Vue.js uses a one-way data flow, meaning that the data should flow from the parent component to the child component, so that the child component can only change the data using the specific events or methods provided by the parent. However, it has a shorthand to achieve two-way data binding v-model which is nothing but a shorthand of v-bind and v-on:input

``` html
	<script src="https://cdn.jsdelivr.net/npm/vue@3.2.45/dist/vue.global.js"></script>
	<div id="app">
		<input v-model="message" placeholder="Enter a message">
		<p>{{ message }}</p>
	</div>
	<script>
		const { createApp } = Vue;
		createApp({
			data() {
				return {
					message: "Hello Vue!",
				};
			},
		}).mount("#app");
	</script>
```

<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@9/dist/mermaid.esm.min.mjs';
mermaid.initialize({ startOnLoad: true });
</script>
​<pre class="mermaid">
graph TD 
A[Client] --> B[Load Balancer] 
B --> C[Server01] 
B --> D[Server02]
</pre>