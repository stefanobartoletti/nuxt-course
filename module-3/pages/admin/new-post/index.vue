<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
      <form @submit.prevent="onSave">
        <AppControlInput v-model="editedPost.author">Author Name</AppControlInput>
        <AppControlInput v-model="editedPost.title">Title</AppControlInput>
        <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>
        <AppControlInput control-type="textarea" v-model="editedPost.content">Content</AppControlInput>

        <AppButton type="submit">Save</AppButton>
        <AppButton type="button" style="margin-left: 10px" btn-style="cancel" @click="onCancel">Cancel</AppButton>
      </form>
    </section>
  </div>
</template>

<script>
import AppControlInput from '@/components/UI/AppControlInput';
import AppButton from '@/components/UI/AppButton';

export default {
    data() {
        return {
            editedPost: {
                author: '',
                title: '',
                thumbnailLink: '',
                content: '',
            }
        }
    },
    components: {
        AppControlInput,
        AppButton
    },
    methods: {
        onSave() {
            // Save the post
            console.log(this.editedPost);
        },
        onCancel() {
            // Navigate back
            this.$router.push('/admin');
        },
    },
};
</script>

<style scoped></style>
