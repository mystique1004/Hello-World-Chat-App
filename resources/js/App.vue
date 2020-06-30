<template>
    <div>
        <router-view />
    </div>
</template>

<script>
import {CometChat} from "@cometchat-pro/chat";
export default {
    created() {
        this.initializeApp();
    },

    methods: {
        initializeApp() {
            let appID = '20617324ff1b1c0';

            let cometChatSettings = new CometChat.AppSettingsBuilder()
                .subscribePresenceForAllUsers()
                .setRegion("us")
                .build();

            CometChat.init(appID, cometChatSettings).then(
                () => {
                    console.log("Initialization completed successfully");
                },
                error => {
                    console.log("Initialization failed with error:", error);
                }
            );
    }
    }
}

</script>

<style scoped>

</style>
