<template>
    <div class="mb-3">
        <label for="octopush-key" class="form-label">API KEY</label>
        <HiddenInput id="octopush-key" v-model="$parent.notification.octopushAPIKey" :required="true" autocomplete="one-time-code"></HiddenInput>
        <label for="octopush-login" class="form-label">API LOGIN</label>
        <input id="octopush-login" v-model="$parent.notification.octopushLogin" type="text" class="form-control" required>
    </div>
    <div class="mb-3">
        <label for="octopush-type-sms" class="form-label">{{ $t("SMS Type") }}</label>
        <select id="octopush-type-sms" v-model="$parent.notification.octopushSMSType" class="form-select">
            <option value="sms_premium">{{ $t("octopushTypePremium") }}</option>
            <option value="sms_low_cost">{{ $t("octopushTypeLowCost") }}</option>
        </select>
        <i18n-t tag="div" keypath="Check octopush prices" class="form-text">
            <a href="https://octopush.com/tarifs-sms-international/" target="_blank">https://octopush.com/tarifs-sms-international/</a>
        </i18n-t>
    </div>
    <div class="mb-3">
        <label for="octopush-phone-number" class="form-label">{{ $t("octopushPhoneNumber") }}</label>
        <input id="octopush-phone-number" v-model="$parent.notification.octopushPhoneNumber" type="text" class="form-control" required>
    </div>
    <div class="mb-3">
        <label for="octopush-sender-name" class="form-label">{{ $t("octopushSMSSender") }}</label>
        <input id="octopush-sender-name" v-model="$parent.notification.octopushSenderName" type="text" minlength="3" maxlength="11" class="form-control">
    </div>

    <i18n-t tag="p" keypath="More info on:" style="margin-top: 8px;">
        <a href="https://octopush.com/api-sms-documentation/envoi-de-sms/" target="_blank">https://octopush.com/api-sms-documentation/envoi-de-sms/</a>
    </i18n-t>
</template>

<script>
import HiddenInput from "../HiddenInput.vue";

export default {
    components: {
        HiddenInput,
    },
};
</script>
