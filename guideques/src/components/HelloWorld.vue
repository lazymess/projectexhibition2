<template>
  <flow-form v-bind:questions="questions" v-bind:language="language" />
</template>

<script>
  // Import necessary components and classes
  import { FlowForm, QuestionModel, QuestionType, ChoiceOption, LanguageModel } from '@ditdot-dev/vue-flow-form'

  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'example',
    components: {
      FlowForm
    },
    data() {
      return {
        language: new LanguageModel({
          // Your language definitions here (optional).
          // You can leave out this prop if you want to use the default definitions.
        }),

        questions: [
          // QuestionModel array
          
          // new QuestionModel({
          //   title: 'Where Do you Stay?',
          //   type: QuestionType.MultipleChoice,
          //   options: [
          //     new ChoiceOption({
          //       label: 'Answer',
                
          //     })
          //   ]
          // })
          new QuestionModel({
            id: 'first_name',
            tagline: 'Hi! Welcome to our questionaire 😊',
            title: 'What is your first name?',
            type: QuestionType.Text,
            required: true,
            placeholder: 'Start typing here...'
          }),
          new QuestionModel({
            id: 'multiple_choice',
            tagline: 'FYI, You can always go back 👈, use the up arrow on the bottom.',
            title: 'Where Do you live?:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'Delhi'
              }),
              new ChoiceOption({
                label: 'Mumbai'
               }),
              new ChoiceOption({
                label: 'Kolkata'
              }),
              new ChoiceOption({
                label: "Chennai"
              })
            ]
          }),
          new QuestionModel({
            id: 'multiple_choice',
            // tagline: 'FYI, You can always go back 👈, use the up arrow on the bottom.',
            title: 'Language:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'English'
              }),
              new ChoiceOption({
                label: 'Hindi'
              }),
            ]
          }),
          new QuestionModel({
            id: 'multiple_choice',
            // tagline: 'FYI, You can always go back 👈, use the up arrow on the bottom.',
            title: 'What are you most interested in:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'Food'
              }),
              new ChoiceOption({
                label: 'Heritage'
               }),
              new ChoiceOption({
                label: 'Nightlife'
              }),
              new ChoiceOption({
                label: 'Tourist Attractions'
              }),
              new ChoiceOption({
                label: 'Hiking'
              }),
              new ChoiceOption({
                label: 'Culture'
              }),
              new ChoiceOption({
                label: 'Hidden Gems in the city'
              })
            ]
          }),
          new QuestionModel({
            id: 'multiple_choice',
            title: 'How Much Experience Do you Have?:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: '1 Year'
              }),
              new ChoiceOption({
                label: '1-5 years'
               }),
              new ChoiceOption({
                label: '5-10 years'
              }),
              new ChoiceOption({
                label: "10 years+"
              })
            ]
          }),new QuestionModel({
            id: 'multiple_choice',

            title: 'What is your preferred time of day to guide:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'Morning'
              }),
              new ChoiceOption({
                label: 'Afternoon'
               }),
              new ChoiceOption({
                label: 'Evening'
              }),
              new ChoiceOption({
                label: "Night"
              }),
              new ChoiceOption({
                label: "Anytime of the day works"
              })
            ]
          }),new QuestionModel({
            id: 'multiple_choice',
            title: 'What will your fee structure be?:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'Hourly'
              }),
              new ChoiceOption({
                label: 'Daily'
               }),
              new ChoiceOption({
                label: 'Project based'
              })
            ]
          }),new QuestionModel({
            id: 'multiple_choice',
            title: 'How can the client contact you:',
            helpTextShow: false,
            type: QuestionType.MultipleChoice,
            multiple: false,
            allowOther: true,
            required: true,
            options: [
              new ChoiceOption({
                label: 'Phone'
              }),
              new ChoiceOption({
                label: 'Email Address'
               }),
              new ChoiceOption({
                label: 'Social Media'
              }),
            ]
          }),
          
          new QuestionModel({
            id: 'multiple_choice_image',
            tagline: "Let's take it one step further...",
            title: 'Tell us what is your favorite social network hangout.',
            helpTextShow: false,
            type: QuestionType.MultiplePictureChoice,
            multiple: true,
            required: true,
            options: [
              new ChoiceOption({
                // imageSrc: require('./assets/images/facebook.png'),
                // imageAlt: 'Facebook logo',
                label: 'Facebook'
              }),
              new ChoiceOption({
                // imageSrc: require('./assets/images/twitter.png'),
                // imageAlt: 'Twitter logo',
                label: 'Twitter'
              }),
              new ChoiceOption({
                // imageSrc: require('./assets/images/instagram.png'),
                // imageAlt: 'Instagram logo',
                label: 'Instagram'
              }),
              new ChoiceOption({
                // imageSrc: require('./assets/images/tiktok.png'),
                // imageAlt: 'TikTok logo',
                label: 'TikTok'
              }),
            ]
          }),
          new QuestionModel({
            id: 'phone',
            title: 'Phone number.',
            type: QuestionType.Phone,
            required: true,
            mask: '#####-#####'
          }),
          new QuestionModel({
            id: 'movies',
            title: 'Say Something about your city',
            type: QuestionType.LongText,
            required: true,
            placeholder: 'Start typing here...'
          }),
          
        ]
      }
    }
  }
</script>

<style>
  /* Import Vue Flow Form base CSS */
  @import '~@ditdot-dev/vue-flow-form/dist/vue-flow-form.css';
  /* Import one of the Vue Flow Form CSS themes (optional) */
  @import '~@ditdot-dev/vue-flow-form/dist/vue-flow-form.theme-minimal.css';
  /* @import '~@ditdot-dev/vue-flow-form/dist/vue-flow-form.theme-green.css'; */
  /* @import '~@ditdot-dev/vue-flow-form/dist/vue-flow-form.theme-purple.css'; */
</style>