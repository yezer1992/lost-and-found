function register() {
    let name = document.getElementById("regName").value;
    let email = document.getElementById("regEmail").value;
    let password = document.getElementById("regPassword").value;

    let users = JSON.parse(localStorage.getItem("users")) || [];
    users.push({name, email, password});
    localStorage.setItem("users", JSON.stringify(users));

    alert("Registered Successfully!");
}

function login() {
    let email = document.getElementById("loginEmail").value;
    let password = document.getElementById("loginPassword").value;

    let users = JSON.parse(localStorage.getItem("users")) || [];
    let user = users.find(u => u.email === email && u.password === password);

    if(user){
        localStorage.setItem("loggedInUser", email);
        window.location.href = "dashboard.html";
    } else {
        alert("Invalid Login");
    }
}

function logout(){
    localStorage.removeItem("loggedInUser");
    window.location.href = "index.html";
}

function addItem(){
    let itemName = document.getElementById("itemName").value;
    let flightNumber = document.getElementById("flightNumber").value;
    let location = document.getElementById("location").value;

    let items = JSON.parse(localStorage.getItem("items")) || [];

    items.push({
        itemName,
        flightNumber,
        location,
        status: "Lost"
    });

    localStorage.setItem("items", JSON.stringify(items));
    displayItems();
}

function displayItems(){
    let items = JSON.parse(localStorage.getItem("items")) || [];
    let list = document.getElementById("itemsList");
    list.innerHTML = "";

    items.forEach((item, index) => {
        list.innerHTML += `
            <div class="card">
                <p><b>Item:</b> ${item.itemName}</p>
                <p><b>Flight:</b> ${item.flightNumber}</p>
                <p><b>Location:</b> ${item.location}</p>
                <p><b>Status:</b> ${item.status}</p>
                ${item.status === "Lost" ? 
                <button onclick="markClaimed(${index})">Mark Claimed</button> : ""}
            </div>
        `;
    });
}

function markClaimed(index){
    let items = JSON.parse(localStorage.getItem("items"));
    items[index].status = "Claimed";
    localStorage.setItem("items", JSON.stringify(items));
    displayItems();
}
