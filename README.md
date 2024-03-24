
### Composition

```
<script setup>
	import {ref} from 'vue'
	const msg = ref('Hello World')
</script>

<template>
	<h1>{{ msg.toLocaleUpperCase() }}</h1>
	<h1>{{ msg ? msg : 'Welcome' }} </h1>
	<h1>{{ msg || 'Welcome' }}</h1>
	<input v-model="msg">
</template>
```

### List Rendering Vue

```
<script setup>
	import {ref} from 'vue'
	
	const header = ref('Shopping List App');

	const items = ref([
		{'id':1, label:'10 party hats'},
		{'id':2, label:'2 board games'},
		{'id':3, label:'20 cups'}
	])
</script>

<template>
	<h1>{{ header }}</h1>
	<ul>
		<li v-for="item in items" :key="item.id">{{ item.label}} </li>
		<li v-for="{id,label} in items" :key="id">{{ label }} </li>
		<li v-for="({id,label},index) in items" :key="index">{{ index }}{{label}} </li>
	</ul>
</template>
```

```
<script setup>
	import {ref} from 'vue'
	
	const header = ref('Shopping List App');

	const items = ref({
		'item-1':{'id':1, label:'10 party hats'},
		'item-2':{'id':2, label:'2 board games'},
		'item-3':{'id':3, label:'20 cups'}
	})
</script>

<template>
	<h1>{{ header }}</h1>
	<ul>
		<li v-for="({id,label},index) in items" :key="id">{{ index }}{{label}} </li>
	</ul>
</template>
```

### User Input 

```
	const newItemPriority = ref('low')
---
method 1
	Priority:
	<label>
		<input type="radio" v-model="newItemPriority" value="low">
		Low
	</label>
	<label>
		<input type="radio" v-model="newItemPriority" value="high">
		High
	</label>
---
method 2
	<label>
		Priority:
		<select v-model="newPriority">
			<option value="low">Low</option>
			<option value="high">High</option>
		</select>
	</label>

---
method 3

	const newItemHighPriority = ref(false)

	<label>
		<input type="checkbox" v-model="newItemHighPriority">High Priority
	</label>

----
method 4

	const iceCreamFlavors = ref([])

	<label>
		<input type="checkbox" value="vanilla" v-model="iceCreamFlavors">Vanilla
	</label>

	<label>
		<input type="checkbox" value="chocolate" v-model="iceCreamFlavors">Chocolate
	</label>

	<label>
		<input type="checkbox" value="strawberry" v-model="iceCreamFlavors">
		Strawberry
	</label>
```
