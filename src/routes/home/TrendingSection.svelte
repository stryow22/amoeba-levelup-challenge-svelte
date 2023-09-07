<script>
	let data = [
	  {
		title: "Card 1",
		image: "https://via.placeholder.com/800x600",
	  },
	  {
		title: "Card 2",
		image: "https://via.placeholder.com/800x600",
	  },
	  {
		title: "Card 3",
		image: "https://via.placeholder.com/800x600",
	  },
	  {
		title: "Card 4",
		image: "https://via.placeholder.com/800x600",
	  },
	  {
		title: "Card 5",
		image: "https://via.placeholder.com/800x600",
	  },
	  {
		title: "Card 6",
		image: "https://via.placeholder.com/800x600",
	  },
	];
  
	let currentCardIndex = 0;
	let numVisibleCards = 4;
	let sliderValue = 0;
  
	function updateCards() {
	  currentCardIndex = sliderValue;
	}
  </script>
  
  <style>
	/* CSS untuk slider */
	.slider {
	  width: 50%; 
	  margin: 10px auto;
	  display: block;
	}  
	
	.card-container {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  margin-top: 100px;
	  /* height: 100vh; */
	  overflow-x: auto;
	  overflow-y: visible;
	}
  
	.card {
	  margin: 0 12px;
	  width: 300px;
	  height: 300px;
	  position: relative;
	  text-align: center;
	}
  
	.card img {
	  width: 100%;
	  height: 100%;
	  object-fit: cover;
	  border-radius: 10px;
	}
  
	.card-title {
	  position: absolute;
	  bottom: 0;
	  left: 0;
	  right: 0;
	  color: white;
	  padding: 8px;
	}
  
	.card-overlay {	
	  bottom: 0;
	  left: 0;
	  right: 0;
	  position: absolute;
	  height: 100%;
	  border-radius: 10px;
	  background-color: rgba(0, 0, 0, 0.5);
	}
	
	@media (max-width: 768px) {
	  .card {
		width: 150px; 
		height: 150px;
	  }
	  
	  .slider {
		width: 100%; 
	  }
	  
	  .card-container {
		justify-content: flex-start; 
	  }
	  
	  .card:nth-child(4) {
		display: none; 
	  }
	}
  </style>
  
  <h1 class="font-bold text-4xl text-center mt-32">Trending Course</h1>

  <div class="card-container">
	{#each data.slice(currentCardIndex, currentCardIndex + numVisibleCards) as item (item.title)}
	  <div class="card">
		<img src={item.image} alt={item.title} />
		<div class="card-overlay"></div>
		<div class="card-title">{item.title}</div>
	  </div>
	{/each}
  </div>
  
  <input
	type="range"
	min="0"
	max={(data.length - numVisibleCards).toString()}
	step="1"
	bind:value={sliderValue}
	on:change={updateCards}
	class="slider"
  />
  