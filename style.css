let tickets = [];

// Load saved tickets
window.onload = function() {
    let saved = localStorage.getItem("tickets");
    if(saved) {
        tickets = JSON.parse(saved);
        displayTickets();
    }
};

function addTicket() {
    let issue = document.getElementById("issue").value;
    let priority = document.getElementById("priority").value;

    if(issue === "") {
        alert("Please enter issue");
        return;
    }

    let time = new Date().toLocaleString(); // current date & time

    let ticket = {
        text: issue,
        status: "Pending",
        priority: priority,
        time: time
    };

    tickets.push(ticket);
    saveTickets();
    displayTickets();

    document.getElementById("issue").value = "";
}function addTicket() {
    let issue = document.getElementById("issue").value;
    let priority = document.getElementById("priority").value;

    if(issue === "") {
        alert("Please enter issue");
        return;
    }

    let time = new Date().toLocaleString(); // current date & time

    let ticket = {
        text: issue,
        status: "Pending",
        priority: priority,
        time: time
    };

    tickets.push(ticket);
    saveTickets();
    displayTickets();

    document.getElementById("issue").value = "";
}

function displayTickets() {
    let list = document.getElementById("ticketList");
    list.innerHTML = "";

    tickets.forEach((t, index) => {
        let li = document.createElement("li");

        li.innerHTML = `
    ${t.text} - 
    <span style="color:${t.status === 'Resolved' ? 'green' : 'black'}">
        ${t.status}
    </span>
    <br>
    Priority: 
    <span style="color:${getPriorityColor(t.priority)}">
        ${t.priority}
    </span>
    <br>
    <small>Time: ${t.time}</small>
    <br>
    <button class="resolve-btn" onclick="markResolved(${index})">Resolve</button>
    <button class="delete-btn" onclick="deleteTicket(${index})">Delete</button>
`;

        list.appendChild(li);
    });
    updateDashboard();
}

function markResolved(index) {
    tickets[index].status = "Resolved";
    saveTickets();
    displayTickets();
}

function deleteTicket(index) {
    tickets.splice(index, 1);
    saveTickets();
    displayTickets();
}

function saveTickets() {
    localStorage.setItem("tickets", JSON.stringify(tickets));
}

function getPriorityColor(priority) {
    if(priority === "High") return "red";
    if(priority === "Medium") return "orange";
    return "green";
}
function updateDashboard() {
    let total = tickets.length;
    let pending = tickets.filter(t => t.status === "Pending").length;
    let resolved = tickets.filter(t => t.status === "Resolved").length;

    document.getElementById("dashboard").innerText =
        `Total: ${total} | Pending: ${pending} | Resolved: ${resolved}`;
}
function searchTickets() {
    let search = document.getElementById("search").value.toLowerCase();

    let filtered = tickets.filter(t => 
        t.text.toLowerCase().includes(search)
    );

    displayFilteredTickets(filtered);
}

function displayFilteredTickets(filteredTickets) {
    let list = document.getElementById("ticketList");
    list.innerHTML = "";

    filteredTickets.forEach((t, index) => {
        let li = document.createElement("li");

        li.innerHTML = `
            ${t.text} - 
            <span style="color:${t.status === 'Resolved' ? 'green' : 'black'}">
                ${t.status}
            </span>
            <br>
            Priority:
            <span style="color:${getPriorityColor(t.priority)}">
                ${t.priority}
            </span>
            <br>
            <small>Time: ${t.time}</small>
        `;

        list.appendChild(li);
    });
}
