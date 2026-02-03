<script setup lang="ts">
import '@jamf/design-system-web-components-next/nav-top-container';
import '@jamf/design-system-web-components-next/nav-logo';

interface TopNavProps {
	mobileBreakpoint?: number;
}

interface TopNavSlots {
	logo: {};
	mobile: {};
	default: {};
}

withDefaults(defineProps<TopNavProps>(), {
	mobileBreakpoint: 1000,
});

defineSlots<TopNavSlots>();
</script>

<template>
	<!-- eslint-disable vue/no-undef-components, vue/no-deprecated-slot-attribute, vue/component-name-in-template-casing -->
	<jamf-nav-top-container :mobile-breakpoint="mobileBreakpoint">
		<jamf-nav-logo slot="logo" title-text="Routines" />
		<slot />
		<div id="topnav-n8n"></div>
		<span v-if="$slots.mobile" slot="mobile">
			<slot name="mobile" />
		</span>
	</jamf-nav-top-container>
</template>
