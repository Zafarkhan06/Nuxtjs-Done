<script>
export default {
  data() {
    return {
      showRegions: false, // Initially hide the regions list
      selectedRegion: null // Initially no region is selected
    };
  },
  methods: {
    toggleRegions() {
      // Toggle the boolean value to show/hide the regions list
      this.showRegions = !this.showRegions;
    },
    selectRegion(region) {
      // Set the selected region
      this.selectedRegion = region;
      // Update the URL based on the selected region
      switch (region) {
        case 'USA':
          this.$router.push('/en-us');
          break;
        case 'UK':
          this.$router.push('/en-uk');
          break;
        case 'China':
          this.$router.push('/en-cn');
          break;
        case 'Pakistan':
          this.$router.push('/en-pk');
          break;
        default:
          break;
      }
      // Hide the regions dropdown after selection
      this.showRegions = false;
    }
  }
};
</script>

<template>
  <div class="min-h-screen px-5 background flex justify-center">
    <div class="container grid mt-5 mb-10 frame">
      <div class="flex justify-between">
        <p class="text-white text-xl font-medium">Netsol</p>
        <div class="drop-down">
          <button class="btn" @click="toggleRegions">Regions</button>
          <div v-if="showRegions" class="dropdown">
            <ul>
              <li class="border-line"@click="selectRegion('USA')">USA</li>
              <li @click="selectRegion('UK')">UK</li>
              <li @click="selectRegion('China')">China</li>
              <li @click="selectRegion('Pakistan')">Pakistan</li>
            </ul>
          </div>
        </div>
      </div>

      <img
        src="assets/images/verticalline.png"
        alt="Netsol Logo"
        class="mt-3"
      />
      <div class="content mt-5">
        <button class="text-lg">News and Insight</button>
        <div class="p3">Latest Insight from Leading Voices</div>
        <div class="p1">
          Solving the world’s problems through technology wouldn’t be possible
          without our most important <br />
          invention: the NetSol. Have a look at our talented teams.
        </div>
        <div class="p2">
          View All News
          <div class="flex justify-center">
            <hr class="w-[7%] flex justify-center" />
          </div>
        </div>
      </div>
      <!-- card images section -->
      <!-- first card -->
      <div class="card flex">
        <div>
          <img src="assets/images/image1.png" />
          <button>News</button>
          <h6>Leasing Life Conference & Awards</h6>
          <div class="pgh">
            Solving the world’s problems through technology wouldn’t be possible
            without our most important invention.
          </div>
        </div>
        <!-- second card -->
        <div>
          <img src="assets/images/Rectangle 530.png" />
          <button>Blog</button>
          <h6>Auto Finance Summit 2023</h6>
          <div class="pgh">
            Solving the world’s problems through technology wouldn’t be possible
            without our most important invention.
          </div>
        </div>
        <!-- third card -->
        <div>
          <img src="assets/images/Rectangle 531.png" />
          <button>Newa</button>
          <h6>Careers at Netsol</h6>
          <div class="pgh">
            Solving the world’s problems through technology wouldn’t be possible
            without our most important invention.
          </div>
        </div>
        <!-- fourth card -->
        <div>
          <img src="assets/images/Rectangle 532.png" />
          <button>Blog</button>
          <h6>Leasing Life Conference & Awards</h6>
          <div class="pgh">
            Solving the world’s problems through technology wouldn’t be possible
            without our most important invention.
          </div>
        </div>
      </div>
      <!-- card end here -->
    </div>
  </div>
</template>
<style>
.frame {
  color: #ffffff;
}
.background {
  /* You can adjust these styles based on your requirements */
  background-image: url("assets/images/background.png"); /* Adjust the path accordingly */
  background-size: cover;
  background-position: center;
  min-height: 100vh; /* Ensures the background covers the entire viewport */
}

.btn {
  width: 157px;
  height: 40px;
  border-radius: 100px;
  border: 1px solid rgba(255, 255, 255, 0.46);
  background-color: rgba(0, 37, 206, 1);
  color: #ffffff;
  box-shadow: 0px 9px 15px 0px #0d93ef inset;
}
.content {
  display: block;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.cards {
  padding-inline: 30px;
}

.content button {
  width: 201px;
  height: 39px;
  top: 146px;
  left: 840px;
  border-radius: 20px;
  border: 1px solid rgba(43, 53, 97, 1);
  padding: 11px, 20px, 11px, 20px;
  gap: 10px;
  color: linear-gradient(180deg, #ffffff 49.51%, #c0c0c0 89.32%);
  background-color: rgba(3, 6, 22, 1);
  color: #ffffff;
}

.content .p3 {
  font: Aeonik;
  font-weight: 500;
  font-size: 40px;
  line-height: 67.2px;
  text-align: Center;
  color: linear-gradient(180deg, #ffffff 49.51%, #c0c0c0 89.32%);
}

.content .p1 {
  display: inline;
  top: 282px;
  left: 406px;
  font-style: Aeonik;
  align-content: center;
}

.content .p2 {
  margin-top: 15px;
}

.card {
  display: flex;
  justify-content: space-between;
  margin-top: 60px;
  height: auto;
  padding-right: 20px;
  gap: 30px;
}
.card:first-of-type {
  padding-left: 20px;
}

.card img {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.card button {
  padding: 6px 12px;
  margin-top: 10px;
  background-color: #1d436b;
  color: #18ebfe;
  border-radius: 5px;
  font-weight: 500;
}

.card h6 {
  font-style: Aeonik;
  font-weight: 500;
  font-size: 18px;
  line-height: 30px;
}

.pgh {
  font-style: Aeonik;
  font-weight: 250;
  font-size: 15px;
  margin-top: 5px;
  line-height: 26px;
}

@media screen and (min-width: 1600px) {
  .card {
    padding-right: 40px;
  }
  .card:first-of-type {
    padding-left: 40px;
  }
}

.dropdown {
  position: absolute;
  margin-top: 5px;
  justify-content: start;
  align-items: start;
  width: 170px;
  height: 200px;
  margin-left: 0px;
  background-color: #092530;
  border-radius: 15px;
  border: 0.5px solid #ffffff;
}

.dropdown ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.dropdown ul li {
  margin-left: 10px;
  margin-right: 10px;
  margin-top: 5px;
  padding: 8px 0px;
  cursor: pointer;
  border-bottom: 1px solid #ffffff;
}

.dropdown ul li:hover {
  color: blue;
  border-bottom: 1px solid blue;
}
</style>
