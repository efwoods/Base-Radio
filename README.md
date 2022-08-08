# Base-Radio-Component
Base Radio Component

## Purpose
Reusable Component

## Explaination
[Vue Mastery: BaseRadio](https://www.vuemastery.com/courses/vue3-forms/base-radio)

[BaseRadio.vue](./BaseRadio.vue)

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


```
<template>
  <input
    type="checkbox" // inputs with this type don't trigger @input events
    :checked="modelValue" // model is bound on checked property rather than value
    @change="$emit('update:modelValue', $event.target.checked)" 
      // change events are triggered (when using selected and onSelected)
      // $event.target.checked is the value of the checked status, ":checked"
    class="field"
  />
  <label v-if="label">{{ label }}</label>
</template>
```

## Prerequisites
None

## Use
```
        <BaseRadio
          v-model="event.pets"
          :value="1"
          label="Yes"
          name="pets"
        />
```
