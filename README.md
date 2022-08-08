# Base-Radio-Component
Base Radio Component

## Purpose
Reusable Component

## Explaination
[Vue Mastery: BaseRadio](https://www.vuemastery.com/courses/vue3-forms/base-radio)

[BaseRadio.vue](./BaseRadio.vue)

### SimpleForm.vue (parent view)
- event structure (defined in App)
```
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
```

### BaseRadio.vue (child component)

```
<template>
  <input
      type="radio"
      :checked="modelValue === value" 
            // checks to know is the current radio button is selected as checked or unchecked 
            // (e.g. ModelValue/selection = 'Cat'; value/radiobutton is 'cat' therefore button is checked; 
            // ModelValue/selection = 'cat'; value/radiobutton is 'dog' therefore button is unchecked;
      :value="value"
      v-bind="$attrs" // enables attribute injection into the correct element (e.g.: 'name'; (see 'Use' section)
      @change="$emit('update:modelValue', value)"
    />
  <label v-if="label">{{ label }}</label>
</template>
```

```
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number], // indicates the model anc accept either Strings or Numbers
      default: ''
    },
    value: {
      type: [String, Number],
      required: true
    }
  }
```

## Prerequisites
None

## Use
```
        <BaseRadio
          v-model="event.pets"
          :value="1"
          label="Yes" // what is seen on the front-end
          name="pets" // name here will create groups between different buttons
        />
```
