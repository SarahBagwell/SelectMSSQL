<h1>SELECT Statements</h1>

<h2>Description</h2>
Sample SELECT statements based on a group project, The Cocoa Shop, completed in the course Data Management.
<br />

<h3>Profit Margin Query:</h3>
Objective: List products with a profit margin less than $2 in descending order. </br>
</br>
<img src="https://i.imgur.com/Ss093pf.png" height="50%" width="50%" alt="Profit Margin Query Results"/>
<h4>SELECT Statement</h4>
<p> 
SELECT product.product_name as "Product Name", product.product_ID as "Product Number", </br>
concat('$',(product.price - product.cost)) as "Unit Profit Margin" </br>
FROM Product </br>
WHERE (product.price - product.cost) < 2 </br>
ORDER BY "Unit Profit Margin" DESC </br>
</p>
<h3>Store Sales Query:</h3>
Objective: A list displaying total sales for each store, highest sales listed first. </br>
</br>
<img src="https://i.imgur.com/tQitLJa.png" height="30%" width="30%" alt="Store Sales Query Results"/>
<h4>SELECT Statement</h4>
<p> 
SELECT location.location_name as "Store Name", location.location_city as "City", </br>
sum(transaction_details.quantity* transaction_details.unit_price) as "Total Sales" </br>
FROM location, Transaction_Details,Transactions </br>
WHERE transaction_details.transaction_ID = transactions.transaction_ID </br>
AND transaction_Details.location_ID = location.location_ID </br>
GROUP BY location.location_name, location.location_city </br>
ORDER BY "Total Sales" DESC </br>
</p>
<h3>Customer List Queries:</h3>
Objective: Create two lists – customers and wholesalers – with their associative contact information.</br>
</br>
<img src="https://i.imgur.com/5beonu2.png" height="80%" width="80%" alt="Customer List Queries Results"/>
<h4>SELECT Statements</h4>
<p> 
SELECT concat(First_Name, ' ', Last_Name) as "Customers", email as "Email", </br>
concat(address, ' ', city, ', ', state, ' ', zip) as "Complete Address" </br>
FROM Customer </br>
WHERE wholesale = 'No' </br>
</br>
SELECT concat(First_Name, ' ', Last_Name) as "Wholesalers", email as "Email", </br>
concat(address, ' ', city, ', ', state, ' ', zip) as "Complete Address", Company </br>
FROM Customer </br>
WHERE wholesale = 'Yes' </br>
</p>
