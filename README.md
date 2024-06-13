# Interactive-Periodic-Table-
Awesome interactive website. Click on an element to display details.
const elements = [
    {
        name: "Hydrogen",
        symbol: "H",
        number: 1,
        mass: 1.008,
        reactivity: "7/10",
        state: "Gas",
        meltingPoint: -259.1,
        boilingPoint: -252.9,
        description: "Hydrogen is the lightest element and the most abundant chemical substance in the universe."
    },
    {
        name: "Helium",
        symbol: "He",
        number: 2,
        mass: 4.0026,
        reactivity: "0/10",
        state: "Gas",
        meltingPoint: -272,
        boilingPoint: -268.9,
        description: "Helium is a colorless, odorless, tasteless, inert gas that heads the noble gas series in the periodic table."
    },
    {
        name: "Lithium",
        symbol: "Li",
        number: 3,
        mass: 6.94,
        reactivity: "8/10",
        state: "Solid",
        meltingPoint: 180.5,
        boilingPoint: 1342,
        description: "Lithium is a soft, silvery-white alkali metal. Under standard conditions, it is the lightest metal and the lightest solid element."
    },
    {
        name: "Beryllium",
        symbol: "Be",
        number: 4,
        mass: 9.0122,
        reactivity: "6/10",
        state: "Solid",
        meltingPoint: 1287,
        boilingPoint: 2471,
        description: "Beryllium is a steel-gray, strong, lightweight and brittle alkaline earth metal."
    },
    {
        name: "Boron",
        symbol: "B",
        number: 5,
        mass: 10.81,
        reactivity: "5/10",
        state: "Solid",
        meltingPoint: 2075,
        boilingPoint: 4000,
        description: "Boron is a metalloid that is essential for plant growth, and is used in glass and ceramics."
    },
    {
        name: "Carbon",
        symbol: "C",
        number: 6,
        mass: 12.011,
        reactivity: "4/10",
        state: "Solid",
        meltingPoint: 3550,
        boilingPoint: 4827,
        description: "Carbon is a nonmetal that is the basis of organic chemistry and is found in all living organisms."
    },
    {
        name: "Nitrogen",
        symbol: "N",
        number: 7,
        mass: 14.007,
        reactivity: "1/10",
        state: "Gas",
        meltingPoint: -210.1,
        boilingPoint: -195.8,
        description: "Nitrogen is a colorless, odorless gas that makes up 78% of the Earth's atmosphere and is a component of all proteins."
    },
    {
        name: "Oxygen",
        symbol: "O",
        number: 8,
        mass: 15.999,
        reactivity: "10/10",
        state: "Gas",
        meltingPoint: -218.8,
        boilingPoint: -183.0,
        description: "Oxygen is a highly reactive nonmetal and an oxidizing agent that readily forms oxides with most elements."
    },
    {
        name: "Fluorine",
        symbol: "F",
        number: 9,
        mass: 18.998,
        reactivity: "10/10",
        state: "Gas",
        meltingPoint: -219.6,
        boilingPoint: -188.1,
        description: "Fluorine is the lightest halogen and exists as a highly toxic pale yellow diatomic gas at standard conditions."
    },
    {
        name: "Neon",
        symbol: "Ne",
        number: 10,
        mass: 20.180,
        reactivity: "0/10",
        state: "Gas",
        meltingPoint: -248.6,
        boilingPoint: -246.1,
        description: "Neon is a colorless, odorless, inert monatomic gas under standard conditions, with about two-thirds the density of air."
    }
    // Add more elements as needed
];

// Function to display element details
function showDetails(element) {
    document.getElementById('element-name').textContent = element.name;
    document.getElementById('element-symbol').textContent = element.symbol;
    document.getElementById('element-number').textContent = element.number;
    document.getElementById('element-mass').textContent = element.mass;
    document.getElementById('element-reactivity').textContent = element.reactivity;
    document.getElementById('element-state').textContent = element.state;
    document.getElementById('element-melting-point').textContent = element.meltingPoint + ' °C';
    document.getElementById('element-boiling-point').textContent = element.boilingPoint + ' °C';
    document.getElementById('element-description').textContent = element.description;
    document.getElementById('element-details').classList.remove('hidden');
    document.getElementById('element-details').style.display = 'block';
}

// Function to close element details
function closeDetails() {
    document.getElementById('element-details').classList.add('hidden');
    document.getElementById('element-details').style.display = 'none';
}

// Function to create element tiles
function createElementTiles() {
    const periodicTable = document.getElementById('periodic-table');
    elements.forEach(element => {
        const elementTile = document.createElement('div');
        elementTile.className = 'element';
        elementTile.innerHTML = `
            <p class="symbol">${element.symbol}</p>
            <p class="name">${element.name}</p>
            <p class="number">${element.number}</p>
        `;
        elementTile.addEventListener('click', () => showDetails(element));
        periodicTable.appendChild(elementTile);
    });
}

// Initialize the periodic table
createElementTiles();
