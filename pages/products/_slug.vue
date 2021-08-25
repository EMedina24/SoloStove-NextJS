<template>


<h1>test</h1>
  
</template>


<script>

import gql from 'graphql-tag'


const products = gql`
  query getProducts($slug: String!) {
     products (where: {slug: $slug}) {
         slug
         title
           }
   }
`
export default {
layout: 'default',

 async asyncData({ app, params }) {

    const client = app.apolloProvider.defaultClient;
    const  slug  = params.slug;

    const res = await client.query({
      query: products,
      variables: {
        slug,
      },
    })

    const   ProductInfo  = res.data;
    console.log(ProductInfo)
    return {
      ProductInfo,
      slug 
    }
  },


  
};


</script>
