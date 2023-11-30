<template>
    <v-card class="mt-5">
        <v-tabs
                v-model="tab"
                bg-color="#5865f2"
        >
            <v-tab v-for="(item,index) in tabs" :key="index" :value="index">{{ item.title }} ${{ index }}</v-tab>
        </v-tabs>

        <v-card-text>
            <v-window v-model="tab">
                <v-window-item v-for="(item,index) in tabs" :key="index" :value="index">
                    <v-card width="400">
                        <v-img
                                class="text-white"
                                cover
                                height="200"
                                src="https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg"
                        >
                            <v-toolbar
                                    color="rgba(0, 0, 0, 0)"
                                    theme="dark"
                            >
                                <template v-slot:prepend>
                                    <v-btn icon="$menu"></v-btn>
                                </template>

                                <v-toolbar-title class="text-h6">
                                    Pack {{index}}
                                </v-toolbar-title>

                                <template v-slot:append>
                                    <v-btn icon="mdi-dots-vertical"></v-btn>
                                </template>
                            </v-toolbar>
                        </v-img>

                        <v-card-text>
                            <v-timeline align="start" density="compact">
                                <v-timeline-item
                                        v-for="message in messages"
                                        :key="message.time"
                                        :dot-color="message.color"
                                        size="x-small"
                                >
                                    <div class="mb-4">
                                        <div class="font-weight-normal">
                                            <strong>{{ message.from }}</strong> @{{ message.time }}
                                        </div>
                                        <div>{{ message.message }}</div>
                                    </div>
                                </v-timeline-item>
                            </v-timeline>
                        </v-card-text>
                    </v-card>
                </v-window-item>


            </v-window>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    data: () => ({
        tab: null,
        tabs: [
            {
                title: 'Pack',
                desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."
            },
            {
                title: 'Pack',
                desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."
            },
            {
                title: 'Pack',
                desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."
            },
            {
                title: 'Pack',
                desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."
            },
        ],
        messages: [
            {
                from: 'You',
                message: `Sure, I'll see you later.`,
                time: '10:42am',
                color: 'deep-purple-lighten-1',
            },
            {
                from: 'John Doe',
                message: 'Yeah, sure. Does 1:00pm work?',
                time: '10:37am',
                color: 'green',
            },
            {
                from: 'You',
                message: 'Did you still want to grab lunch today?',
                time: '9:47am',
                color: 'deep-purple-lighten-1',
            },
        ],
    }),
}
</script>
