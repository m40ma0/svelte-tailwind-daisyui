<script>
	export let title;
	export let image;
	export let alt;
	export let popupTitle;
	export let popupDescription;
    export let website = ""
    import '../global.css'
</script>

<div class="ui-card relative overflow-hidden w-[350px] h-[200px] rounded">
    <div class="flex justify-center align-center mt-8">
        <img src={image} {alt} class="w-[140px] h-[140px]" />
    </div>
	<div class="description absolute bottom-0 left-0 w-full text-center text-white p-4">
		<h3>{title}</h3>
		<br />

		<!-- Learn more button -->
		<div class="buttonContainer modal-button">
			<button>
				<div>
					<span class="circle">
						<span class="icon arrow" />
					</span>
				</div>
				<label for="my-modal" class="poppins-semibold buttonText hover:cursor-pointer">Learn More</label>
			</button>
		</div>
	</div>
</div>

<!-- Modal -->
<div class="modals">
	<input type="checkbox" id="my-modal" class="modal-toggle" />
	<label for="my-modal" class="modal cursor-pointer sm:modal-middle">
		<label class="modal-box relative border-0" for="">
			<div class="card ring-0">
				<div class="card-body flex flex-col gap-4">
                    <div class="flex align-center gap-4">
                        <img src={image} {alt} class="w-12 h-12">
                        <h2 class="card-title text-secondary poppins-bold">{popupTitle}</h2>
                    </div>
					<span>{popupDescription ?? ''}</span>
                    <div class="divider m-0"></div>
                    <span>
                        <span class="poppins-semibold">Website: </span>
                        <a href={website} target="_blank" class="hover:cursor-pointer hover:underline">
                            {website}
                        </a>
                    </span>
				</div>
			</div>
		</label>
	</label>
</div>

<style>
	.rounded {
		border-radius: 5%;
	}

	button {
		position: relative;
		border: 0;
		display: inline-block;
		width: 12rem;
		height: auto;
		cursor: pointer;
		outline: none;
		vertical-align: middle;
		background: transparent;
	}

	.buttonText {
		position: absolute;
		inset: 0;
		padding: 0.55rem 0;
		margin-left: 1.85rem;
		color: #6c61eb;
		line-height: 1.6;
		text-align: center;
		transition: all 0.25s ease-in-out;
	}

	.circle {
		position: relative;
		display: block;
		margin: 0;
		width: 3rem;
		height: 3rem;
		background: #03045e;
		border-radius: 1.625rem;
		transition: all 0.4s ease-in-out;
	}

	.icon {
		position: absolute;
		top: 0;
		bottom: 0;
		margin: auto;
		background: white;
	}

	.arrow {
		left: 0.625rem;
		width: 1.125rem;
		height: 0.125rem;
		background: none;
		transition: all 0.4s ease-in-out;
	}

	.arrow::before {
		content: '';
		position: absolute;
		top: -0.3rem;
		right: 0.0625rem;
		width: 0.625rem;
		height: 0.625rem;
		border-top: 0.125rem solid white;
		border-right: 0.125rem solid white;
		transform: rotate(45deg);
	}

	button:hover .circle {
		width: 100%;
	}

	button:hover .arrow {
		background: white;
		transform: translateX(1rem);
	}

	button:hover .buttonText {
		color: white;
	}
	/* End Learn more icon */

	/* Card display */
	.ui-card {
		transition: all 0.3s ease-out;
		background: #cccccc;
	}

	.ui-card img {
		transform: scale(1.3);
		transition: all 0.3s ease-out;
	}

	.ui-card:hover img {
		transform: scale(1.1) translateY(-20px);
		opacity: 0.3;
	}

	.description h3 {
        color: #03045e;
		font-weight: 700;
		font-size: 32px;
		margin: 0 0 20px;
		transform: translateY(30px);
		opacity: 0;
		transition: all 0.3s ease-out 0.15s;
	}

	.buttonContainer {
		transform: translateY(30px);
		opacity: 0;
		transition: all 0.3s ease-out;
	}

	.ui-card:hover .description h3 {
		opacity: 1;
		transform: translateY(0px);
	}

	.ui-card:hover .buttonContainer {
		opacity: 1;
		transform: translateY(0px);
	}
</style>
