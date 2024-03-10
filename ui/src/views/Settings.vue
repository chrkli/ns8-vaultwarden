<!--
  Copyright (C) 2023 Nethesis S.r.l.
  SPDX-License-Identifier: GPL-3.0-or-later
-->
<template>
  <cv-grid fullWidth>
    <cv-row>
      <cv-column class="page-title">
        <h2>{{ $t("settings.title") }}</h2>
      </cv-column>
    </cv-row>
    <cv-row v-if="error.getConfiguration">
      <cv-column>
        <NsInlineNotification
          kind="error"
          :title="$t('action.get-configuration')"
          :description="error.getConfiguration"
          :showCloseButton="false"
        />
      </cv-column>
    </cv-row>
    <cv-row>
      <cv-column>
        <cv-tile light>
          <cv-form @submit.prevent="configureModule">
            <cv-text-input
              :label="$t('settings.domain')"
              v-model="Domain"
              placeholder="vaultwarden.example.com"
              :disabled="loading.getConfiguration || loading.configureModule"
              :invalid-message="error.domain"
              ref="Domain"
            ></cv-text-input>
            <cv-text-input
              :label="$t('settings.path')"
              v-model="Path"
              placeholder="/webvault"
              :disabled="loading.getConfiguration || loading.configureModule"
              :invalid-message="error.path"
              ref="Path"
            ></cv-text-input>
            <cv-text-input
              :label="$t('settings.orgname')"
              v-model="OrgName"
              placeholder="NS8-Vaultwarden"
              :disabled="loading.getConfiguration || loading.configureModule"
              :invalid-message="error.orgname"
	      ref="OrgName"
            ></cv-text-input>
            <cv-toggle
              value="InvitationsEnabled"
              :label="$t('settings.invitations')"
              v-model="InvitationsEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="WebvaultEnabled"
              :label="$t('settings.webvault')"
              v-model="WebvaultEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="WebsocketEnabled"
              :label="$t('settings.websocket')"
              v-model="WebsocketEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="SendsEnabled"
              :label="$t('settings.sends')"
              v-model="SendsEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="EmergencyAccessEnabled"
              :label="$t('settings.emergencyaccess')"
              v-model="EmergencyAccessEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="IconDownloadEnabled"
              :label="$t('settings.icondownload')"
              v-model="IconDownloadEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="SignupsEnabled"
              :label="$t('settings.signups')"
              v-model="SignupsEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="letsEncryptEnabled"
              :label="$t('settings.lets_encrypt')"
              v-model="LetsEncryptEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-toggle
              value="HttpToHttpsEnabled"
              :label="$t('settings.http_to_https')"
              v-model="HttpToHttpsEnabled"
              :disabled="loading.getConfiguration || loading.configureModule"
              class="mg-bottom"
            >
              <template slot="text-left">{{
                $t("settings.disabled")
              }}</template>
              <template slot="text-right">{{
                $t("settings.enabled")
              }}</template>
            </cv-toggle>
            <cv-row v-if="error.configureModule">
              <cv-column>
                <NsInlineNotification
                  kind="error"
                  :title="$t('action.configure-module')"
                  :description="error.configureModule"
                  :showCloseButton="false"
                />
              </cv-column>
            </cv-row>
            <NsButton
              kind="primary"
              :icon="Save20"
              :loading="loading.configureModule"
              :disabled="loading.getConfiguration || loading.configureModule"
              >{{ $t("settings.save") }}</NsButton
            >
          </cv-form>
        </cv-tile>
      </cv-column>
    </cv-row>
  </cv-grid>
</template>

<script>
import to from "await-to-js";
import { mapState } from "vuex";
import {
  QueryParamService,
  UtilService,
  TaskService,
  IconService,
  PageTitleService,
} from "@nethserver/ns8-ui-lib";

export default {
  name: "Settings",
  mixins: [
    TaskService,
    IconService,
    UtilService,
    QueryParamService,
    PageTitleService,
  ],
  pageTitle() {
    return this.$t("settings.title") + " - " + this.appName;
  },
  data() {
    return {
      q: {
        page: "settings",
      },
      urlCheckInterval: null,
      Domain: "",
      Path: "",
      OrgName: "",
      InvitationsEnabled: true,
      WebvaultEnabled: true,
      WebsocketEnabled: true,
      SendsEnabled: true,
      EmergencyAccessEnabled: true,
      IconDownloadEnabled: true,
      SignupsEnables: true,
      LetsEncryptEnabled: false,
      HttpToHttpsEnabled: false,
      loading: {
        getConfiguration: false,
        configureModule: false,
      },
      error: {
        getConfiguration: "",
        configureModule: "",
        Domain: "",
        Path: "",
        lets_encrypt: "",
        http_to_https: "",
      },
    };
  },
  computed: {
    ...mapState(["instanceName", "core", "appName"]),
  },
  beforeRouteEnter(to, from, next) {
    next((vm) => {
      vm.watchQueryData(vm);
      vm.urlCheckInterval = vm.initUrlBindingForApp(vm, vm.q.page);
    });
  },
  beforeRouteLeave(to, from, next) {
    clearInterval(this.urlCheckInterval);
    next();
  },
  created() {
    this.getConfiguration();
  },
  methods: {
    async getConfiguration() {
      this.loading.getConfiguration = true;
      this.error.getConfiguration = "";
      const taskAction = "get-configuration";
      const eventId = this.getUuid();

      // register to task error
      this.core.$root.$once(
        `${taskAction}-aborted-${eventId}`,
        this.getConfigurationAborted
      );

      // register to task completion
      this.core.$root.$once(
        `${taskAction}-completed-${eventId}`,
        this.getConfigurationCompleted
      );

      const res = await to(
        this.createModuleTaskForApp(this.instanceName, {
          action: taskAction,
          extra: {
            title: this.$t("action." + taskAction),
            isNotificationHidden: true,
            eventId,
          },
        })
      );
      const err = res[0];

      if (err) {
        console.error(`error creating task ${taskAction}`, err);
        this.error.getConfiguration = this.getErrorMessage(err);
        this.loading.getConfiguration = false;
        return;
      }
    },
    getConfigurationAborted(taskResult, taskContext) {
      console.error(`${taskContext.action} aborted`, taskResult);
      this.error.getConfiguration = this.$t("error.generic_error");
      this.loading.getConfiguration = false;
    },
    getConfigurationCompleted(taskContext, taskResult) {
      this.loading.getConfiguration = false;
      const config = taskResult.output;
      this.Domain = config.domain;
      this.Path = config.path;
      this.OrgName = config.orgname;
      this.InvitationsEnabled = config.invitations;
      this.WebvaultEnabled = config.webvault;
      this.WebsocketEnabled = config.websocket;
      this.SendsEnabled = config.sends;
      this.EmergencyAccessEnabled = config.emergencyaccess;
      this.IconDownloadEnabled = config.icondownload;
      this.SignupsEnabled = config.signups;
      this.LetsEncryptEnabled = config.lets_encrypt;
      this.HttpToHttpsEnabled = config.http_to_https;
      this.focusElement("Domain");
    },
    validateConfigureModule() {
      this.clearErrors(this);
      let isValidationOk = true;
      
      if (!this.Domain) {
        this.error.domain = this.$t("common.required");
        if (isValidationOk) {
          this.focusElement("Domain");
          isValidationOk = false;
        }
      }

      if (!this.Path) {
        this.error.domain = this.$t("common.required");
        if (isValidationOk) {
          this.focusElement("Path");
          isValidationOk = false;
        }
      }
     
      if (!this.OrgName) {
        this.error.orgname = this.$t("common.required");
        if (isValidationOk) {
          this.focusElement("OrgName");
          isValidationOk = false;
        }
      }
      return isValidationOk;
    },
    configureModuleValidationFailed(validationErrors) {
      this.loading.configureModule = false;

      for (const validationError of validationErrors) {
        const param = validationError.parameter;

        // set i18n error message
        this.error[param] = this.$t("settings." + validationError.error);
      }
    },
    async configureModule() {
      const isValidationOk = this.validateConfigureModule();
      if (!isValidationOk) {
        return;
      }

      this.loading.configureModule = true;
      const taskAction = "configure-module";
      const eventId = this.getUuid();

      // register to task error
      this.core.$root.$once(
        `${taskAction}-aborted-${eventId}`,
        this.configureModuleAborted
      );

      // register to task validation
      this.core.$root.$once(
        `${taskAction}-validation-failed-${eventId}`,
        this.configureModuleValidationFailed
      );

      // register to task completion
      this.core.$root.$once(
        `${taskAction}-completed-${eventId}`,
        this.configureModuleCompleted
      );

      const res = await to(
        this.createModuleTaskForApp(this.instanceName, {
          action: taskAction,
          data: {
            domain: this.Domain,
            path: this.Path,
            orgname: this.OrgName,
            invitations: this.InvitationsEnabled,
            webvault: this.WebvaultEnabled,
            websocket: this.WebsocketEnabled,
            sends: this.SendsEnabled,
            emergencyaccess: this.EmergencyAccessEnabled,
            icondownload: this.IconDownloadEnabled,
            signups: this.SignupsEnabled,
            lets_encrypt: this.LetsEncryptEnabled,
            http_to_https: this.HttpToHttpsEnabled,
          },
          extra: {
            title: this.$t("settings.configure_instance", {
              instance: this.instanceName,
            }),
            description: this.$t("common.processing"),
            eventId,
          },
        })
      );
      const err = res[0];

      if (err) {
        console.error(`error creating task ${taskAction}`, err);
        this.error.configureModule = this.getErrorMessage(err);
        this.loading.configureModule = false;
        return;
      }
    },
    configureModuleAborted(taskResult, taskContext) {
      console.error(`${taskContext.action} aborted`, taskResult);
      this.error.configureModule = this.$t("error.generic_error");
      this.loading.configureModule = false;
    },
    configureModuleCompleted() {
      this.loading.configureModule = false;

      // reload configuration
      this.getConfiguration();
    },
  },
};
</script>

<style scoped lang="scss">
@import "../styles/carbon-utils";
</style>
