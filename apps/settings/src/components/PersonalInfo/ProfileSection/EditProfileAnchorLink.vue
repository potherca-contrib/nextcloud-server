<!--
	- @copyright 2021 Christopher Ng <chrng8@gmail.com>
	-
	- @author Christopher Ng <chrng8@gmail.com>
	-
	- @license GNU AGPL version 3 or any later version
	-
	- This program is free software: you can redistribute it and/or modify
	- it under the terms of the GNU Affero General Public License as
	- published by the Free Software Foundation, either version 3 of the
	- License, or (at your option) any later version.
	-
	- This program is distributed in the hope that it will be useful,
	- but WITHOUT ANY WARRANTY; without even the implied warranty of
	- MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
	- GNU Affero General Public License for more details.
	-
	- You should have received a copy of the GNU Affero General Public License
	- along with this program. If not, see <http://www.gnu.org/licenses/>.
	-
-->

<template>
	<a
		:class="{ disabled }"
		href="#profile-visibility"
		v-on="$listeners">
		<ChevronDownIcon
			class="anchor-icon"
			decorative
			title=""
			:size="22" />
		{{ t('settings', 'Edit your Profile visibility') }}
	</a>
</template>

<script>
import ChevronDownIcon from 'vue-material-design-icons/ChevronDown'

export default {
	name: 'EditProfileAnchorLink',

	components: {
		ChevronDownIcon,
	},

	props: {
		profileEnabled: {
			type: Boolean,
			required: true,
		},
	},

	computed: {
		disabled() {
			return !this.profileEnabled
		},
	},
}
</script>

<style lang="scss">
html {
	scroll-behavior: smooth;

	@media screen and (prefers-reduced-motion: reduce) {
		scroll-behavior: auto;
	}
}
</style>

<style lang="scss" scoped>
a {
	display: block;
	height: 44px;
	width: 290px;
	line-height: 44px;
	padding: 0 16px;
	margin: 14px auto;
	border-radius: var(--border-radius-pill);
	opacity: 0.4;
	background-color: transparent;

	.anchor-icon {
		display: inline-block;
		vertical-align: middle;
		margin-top: 6px;
		margin-right: 8px;
	}

	&:hover {
		opacity: 0.8;
		background-color: rgba(127, 127, 127, .25);
	}

	&.disabled {
		pointer-events: none;
	}
}
</style>
