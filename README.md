googdu
it's fun

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GoogDuck Search</title>
<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #fff;
  color: #202124;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

nav {
  display: flex;
  justify-content: flex-end;
  padding: 20px 30px;
  gap: 22px;
  font-size: 14px;
}

nav a {
  color: #333;
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

main {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
  margin-top: -65px;
}

.logo {
  font-size: clamp(55px, 10vw, 90px);
  font-weight: 600;
  letter-spacing: -5px;
  margin-bottom: 30px;
}

.logo span:nth-child(1) { color: #4285f4; }
.logo span:nth-child(2) { color: #ea4335; }
.logo span:nth-child(3) { color: #fbbc05; }
.logo span:nth-child(4) { color: #4285f4; }
.logo span:nth-child(5) { color: #34a853; }
.logo span:nth-child(6) { color: #ea4335; }

.logo small {
  font-size: 17px;
  letter-spacing: 0;
  color: #777;
  vertical-align: bottom;
  margin-left: 5px;
}

.search-box {
  width: min(580px, 95vw);
  height: 52px;
  border: 1px solid #dfe1e5;
  border-radius: 30px;
  display: flex;
  align-items: center;
  padding: 0 18px;
  transition: box-shadow .2s;
}

.search-box:hover,
.search-box:focus-within {
  box-shadow: 0 1px 6px rgba(32,33,36,.28);
  border-color: transparent;
}

.search-box input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 16px;
  padding: 10px;
  min-width: 0;
}

.search-icon {
  color: #9aa0a6;
  font-size: 20px;
}

.buttons {
  display: flex;
  gap: 12px;
  margin-top: 28px;
}

button {
  border: 1px solid #f8f9fa;
  background: #f8f9fa;
  border-radius: 5px;
  padding: 11px 18px;
  color: #3c4043;
  cursor: pointer;
  font-size: 14px;
}

button:hover {
  border: 1px solid #dadce0;
}

footer {
  background: #f2f2f2;
  color: #70757a;
  padding: 18px 30px;
  font-size: 14px;
}

footer a {
  color: #70757a;
  text-decoration: none;
  margin-right: 20px;
}

footer a:hover {
  text-decoration: underline;
}
</style>
</head>

<body>

<nav>
  <a href="https://duckduckgo.com/">DuckDuckGo</a>
  <a href="https://github.com/">GitHub</a>
</nav>

<main>
  <div class="logo">
    <span>G</span><span>o</span><span>o</span><span>g</span><span>D</span><span>u</span><small>Search</small>
  </div>

  <form id="searchForm">
    <div class="search-box">
      <span class="search-icon">⌕</span>
      <input
        type="text"
        id="searchInput"
        placeholder="Search the web with GoogDuck"
        autocomplete="off"
        required
      >
    </div>

    <div class="buttons">
      <button type="submit">GoogDuck Search</button>
      <button type="button" onclick="luckySearch()">
        I'm Feeling Lucky
      </button>
    </div>
  </form>
</main>

<footer>
  <a href="https://duckduckgo.com/">Powered by DuckDuckGo</a>
  <a href="https://duckduckgo.com/privacy">Privacy</a>
</footer>

<script>
const form = document.getElementById("searchForm");
const input = document.getElementById("searchInput");

form.addEventListener("submit", function(e) {
  e.preventDefault();

  const query = input.value.trim();

  if (query) {
    window.location.href =
      "https://duckduckgo.com/?q=" + encodeURIComponent(query);
  }
});

function luckySearch() {
  const query = input.value.trim();

  if (query) {
    window.location.href =
      "https://duckduckgo.com/?q=" +
      encodeURIComponent(query) + "&ia=web";
  }
}
</script>

</body>
</html>
