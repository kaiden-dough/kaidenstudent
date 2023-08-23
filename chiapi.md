# Chinese Foods API
<html>
    <input type="text" id="searchBox" placeholder="Enter a Chinese Food">
    <button onclick="search()">Enter</button>
    <div id="container"></div>
</html>
<script>
    let results = []
    async function fetchData() {
        const url = 'https://chinese-food-db.p.rapidapi.com/';
        const options = {
            method: 'GET',
            headers: {
                'X-RapidAPI-Key': '460f88d59amsh76ca8a31ce1e3e8p1980d4jsn45f1c423170f',
                'X-RapidAPI-Host': 'chinese-food-db.p.rapidapi.com'
            }
        };
        try {
            const response = await fetch(url, options);
            const result = await response.text();
            results = JSON.parse(result)
            // console.log(result);
        } catch (error) {
            console.error(error);
        }
    }
    fetchData()
    async function search() {
        const searchText = document.getElementById("searchBox").value;
        const searchResults = results.filter(item => item.title.toLowerCase().includes(searchText.toLowerCase()));
        console.log("Search results:", searchResults);
        tableMake(searchResults)
    }
    function tableMake(searchResults){
        console.log("se")
        let container = document.getElementById("container");
        container.innerHTML=""
        let table = document.createElement("table");
        let cols = Object.keys(searchResults[0]);
        let thead = document.createElement("thead");
        let tr = document.createElement("tr");
        cols.forEach((item) => {
            if (item == "id"){
                return;
            }
            let th = document.createElement("th");
            th.innerText = item;
            tr.appendChild(th);
        });
        thead.appendChild(tr);
        table.append(tr)
        searchResults.forEach((item) => {
            let tr = document.createElement("tr");
            let vals = Object.values(item);
            vals.forEach((elem) => {
                if (!isNaN(elem)){
                    return;
                }
                let td = document.createElement("td");
                if(elem.includes("https://apipics.s3.amazonaws.com/chinese_recipes_api/")){
                    console.log("el")
                    let pic = '<img src="'+elem+'" height="100" width="100">'
                    td.innerHTML = pic
                } else{
                    console.log("hdb")
                    td.innerText = elem;
                }
                tr.appendChild(td);
            });
            table.appendChild(tr);
         });
         container.appendChild(table)
    }

</script>