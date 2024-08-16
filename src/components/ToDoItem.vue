<script>
  import uniqueId from "lodash.uniqueid";
  export default {
    props: {
      label: { required: true, type: String },
      done: { default: false, type: Boolean },
      name:{default: 'defaultName', type: String},
      startDate:{default: 'defaultStartDate',type:String},
      endDate:{default: 'defaultEndDate',type:String}
    },
    
  };
</script>

<template>
  <tr>
    <td ><input type="checkbox" :id="id" :checked="isDone" /></td>
    <td ><label>{{label}}</label></td>
    <td ><label>{{name}}</label></td>
    <td ><label>{{startDate}}</label></td>
    <td ><label>{{endDate}}</label></td>
  </tr>
</template>
