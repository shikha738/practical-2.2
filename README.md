# practical-2.2
Dynamic Product Filter with Dropdown using JavaScript DOM Manipulation
# practicle-2.2
Dynamic Product Filter with Dropdown using JavaScript DOM Manipulation
<img width="529" height="425" alt="Screenshot 2025-09-08 120846" src="https://github.com/user-attachments/assets/3aa5a8f5-42a9-40fa-ba36-4bbf4ff01855" />
<img width="527" height="264" alt="Screenshot 2025-09-08 120858" src="https://github.com/user-attachments/assets/052ee065-ccc2-4385-8f28-88e705435d31" />
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product List Filter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin: 20px;
    }

    .container {
      width: 500px;
      border: 2px solid black;
      padding: 15px;
      margin-bottom: 20px;
    }

    h2 {
      font-size: 20px;
      margin-bottom: 10px;
    }

    select {
      padding: 5px;
      margin-bottom: 15px;
      font-size: 14px;
    }

    ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    li {
      background-color: #f8f8f8;
      padding: 10px;
      margin-bottom: 5px;
      border: 1px solid #ddd;
      border-radius: 4px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Product List</h2>
    <label for="category1">Filter by Category: </label>
    <select id="category1">
      <option value="All">All</option>
      <option value="Clothing">Clothing</option>
      <option value="Electronics">Electronics</option>
      <option value="Books">Books</option>
    </select>
    <ul id="list1"></ul>
  </div>

  <div class="container">
    <h2>Product List</h2>
    <label for="category2">Filter by Category: </label>
    <select id="category2">
      <option value="Clothing">Clothing</option>
      <option value="Books">Books</option>
    </select>
    <ul id="list2"></ul>
  </div>

  <script>
    // Product data
    const products = [
      { name: "T-Shirt", category: "Clothing" },
      { name: "Jeans", category: "Clothing" },
      { name: "Headphones", category: "Electronics" },
      { name: "Smartphone", category: "Electronics" },
      { name: "Novel", category: "Books" },
      { name: "Cookbook", category: "Books" }
    ];

    // Function to filter products and display them
    function updateProductList(selectId, listId) {
      const category = document.getElementById(selectId).value;
      const list = document.getElementById(listId);

      // Clear the previous list
      list.innerHTML = "";

      // Filter products based on the selected category
      const filteredProducts =
        category === "All"
          ? products
          : products.filter(p => p.category === category);

      // Display filtered products
      filteredProducts.forEach(product => {
        const li = document.createElement("li");
        li.textContent = product.name;
        list.appendChild(li);
      });
    }

    // Initialize first dropdown
    document.getElementById("category1").addEventListener("change", () => {
      updateProductList("category1", "list1");
    });

    // Initialize second dropdown
    document.getElementById("category2").addEventListener("change", () => {
      updateProductList("category2", "list2");
    });

    // Load initial data
    updateProductList("category1", "list1");
    updateProductList("category2", "list2");
  </script>
</body>
</html>
