<template>
  <Tutorial/>
</template>


<script>

import gql from 'graphql-tag'


export default {

 apollo: {
    products: gql`
       query getProducts{
         products {
         slug
           }

      }`
  },



  
};


</script>
