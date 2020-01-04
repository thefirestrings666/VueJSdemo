<template>
    <button @click="onClick" class="Button">
        <slot>Button</slot>
    </button>
</template>

<script>
export default {
    props: {
        onClick: {
            type: Function,
            required: true
        }
    }
}
</script>

<style>
.Button {
	box-shadow:inset 0px 1px 0px 0px #ffffff;
	background:linear-gradient(to bottom, #ededed 5%, #dfdfdf 100%);
	background-color:#ededed;
	border-radius:6px;
	border:1px solid #dcdcdc;
	display:inline-block;
	cursor:pointer;
	color:#777777;
	font-family:Arial;
	font-size:15px;
	font-weight:bold;
	padding:9px 24px;
	text-decoration:none;
	text-shadow:0px 1px 0px #ffffff;
}
.Button:hover {
	background:linear-gradient(to bottom, #dfdfdf 5%, #ededed 100%);
	background-color:#dfdfdf;
}
.Button:active {
	position:relative;
	top:1px;
}

</style>