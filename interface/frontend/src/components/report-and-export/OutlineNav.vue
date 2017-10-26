<template lang="html">
	<div class="outline-nav">
		<h1>Outline</h1>
		<ul>
			<li v-for='outline in outlines'>
				<a  href='#' @click='jumpToOutline(outline)'>{{ outline }}</a>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
  props: ['outlines'],
  methods: {
    jumpToOutline (outline) {

    }
  }
}
</script>

<style lang="scss">
.outline-nav {
    h1 {
				color: #F6F6EF;
				background-color: #34363A;

				font-size: 2.5em;

				line-height: 2em;
				padding-left: 1em;
        font-weight: normal;
        letter-spacing: 2px;
    }
    ul {
        list-style: none;
        margin-top: 0;
        padding: 0;

        li {
            padding-left: 4em;

						background-color: #383B42;

            border-bottom: 1px solid #2E3036;

						transition: 0.6s;

	          &:hover {
								cursor: pointer;
                background-color: #454952;
            }

            &:hover a {
							color: #fff;
            }

            a {
								font-size: 1.20em;
								text-decoration: none;
                line-height: 55px;

                position: relative;
                letter-spacing: 1px;
                transition: all 0.6s;
								color: #b3b3b3;
            }

						&.active {
							background-color: white;
							a {
								color: black;
							}
						}
        }
    }
}
</style>
