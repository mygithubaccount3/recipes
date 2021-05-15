<template>
  <section class="single-recipe">
      <h1>{{ recipe.title }}</h1>
      <div>
          <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
      </div>
      <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
    asyncData(context) {
                return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: '1',
                            title: 'Delicious Food',
                            previewText: 'Awesome Food',
                            descriptionText: 'This is really a delicious meal',
                            thumbnail: 'https://thumbs-prod.si-cdn.com/cAU0hdDob45w_75sItCT68WXbZQ=/800x600/filters:no_upscale()/https://public-media.si-cdn.com/filer/c5/d1/c5d13e71-f316-4b68-ac23-99b6384f4792/istock-602301816.jpg'
                        },
                        {
                            id: '2',
                            title: 'Delicious Food',
                            previewText: 'Awesome Food',
                            descriptionText: 'This is really a delicious meal',
                            thumbnail: 'https://health.clevelandclinic.org/wp-content/uploads/sites/3/2016/10/foodJointPainRelief-142336977-770x533-1.jpg'
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
.single-recipe {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column;
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 100%;
}

</style>