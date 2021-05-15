<template>
  <section class="recipes">
      <Recipe
        v-for="recipe in recipes"
        :key="recipe.id"
        :thumbnail="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText" />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },

    asyncData() {
                return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: '1',
                            title: 'Delicious Food',
                            previewText: 'Awesome Food',
                            thumbnail: 'https://thumbs-prod.si-cdn.com/cAU0hdDob45w_75sItCT68WXbZQ=/800x600/filters:no_upscale()/https://public-media.si-cdn.com/filer/c5/d1/c5d13e71-f316-4b68-ac23-99b6384f4792/istock-602301816.jpg'
                        },
                        {
                            id: '2',
                            title: 'Delicious Food',
                            previewText: 'Awesome Food',
                            thumbnail: 'https://health.clevelandclinic.org/wp-content/uploads/sites/3/2016/10/foodJointPainRelief-142336977-770x533-1.jpg'
                        }
                    ]
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
.recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}
</style>