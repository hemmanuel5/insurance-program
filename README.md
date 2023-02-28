<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8"> 
		<title>Insurance Processing</title>
		<!-- Hephzibah Emmanuel, Section 18 !! -->
    	<!--On my honor, I have neither received nor given any unauthorized assistance on this assignment.-->
		<style>
			body {background-color: blanchedalmond; color: darkblue}
		</style>
		<script>
			var homeInsurance = 0;
        	var autoInsurance = 0;
       		var additionalFlood = 0;
        	var deductible = 0;
        	var discount = 0;
		</script>
 	</head>
	<body>
		<h1>Insurance Processing</h1>
		
		<h2>Inputs</h2>
		<p>
 	  	 	<b>Insurance Type:</b> 
			<input type = "radio" id = "auto" name = "insuranceType" 
			onclick = ""> Auto 
			<input type = "radio" id = "home" name = "insuranceType" 
			onclick = ""> Home 
		</p>	
 	  	
		<table>
			<tr>
				<th><h3>Insurance Data</h3></th>
				<th><h3>Answer</h3></th>
			</tr>
			<tr>
				<td>Home Ownership: (O)wn/(R)ent</td>
				<td><input type="text" id="homeType" onchange ='' ></td>	
						
			</tr>
			<tr>
				<td>Flood Insurance: (Y)es/(N)o</td>
				<td><input type="text" id="floodInsurance" onchange = '' ></td>
			</tr>
			<tr>
				<td>No Deductible: (Y)es/(N)o</td>
				<td><input type="text" id="noDeductible" onchange = '' ></td>
			</tr>
			<tr>
				<td>Payment Type: (S)ingle/(M)onthly</td>
				<td><input type="text" id="paymentType" onchange = '' ></td>
			</tr>
		</table>


		<p>
 	  	    <input type = "button" id = "process" value = "Process" 
			onclick = 
			'
				if (home.checked)
				{
					homeType.value = (homeType.value).toUpperCase();
					if (homeType.value == "O") 
					{	
						homeInsurance = 2000;
					}	
					else if (homeType.value == "R")
					{
						homeInsurance = 500;
					}
					
					floodInsurance.value = (floodInsurance.value).toUpperCase();
					if (floodInsurance.value == "Y")
					{
						additionalFlood = 300;
					}
					else if (floodInsurance.value == "N")
					{
						additionalFlood = 0;
					}
				}
				else if (auto.checked)
				{
					autoInsurance = 1000;
					noDeductible.value = (noDeductible.value).toUpperCase();
					if (noDeductible.value == "Y")
					{
						deductible = 400;
					}
					else if (noDeductible.value == "N")
					{
						deductible = 0;
					}
				}
	
				paymentType.value = (paymentType.value).toUpperCase();
				if (paymentType.value == "S")
				{
					discount = 0.03;
				}
				else if (paymentType.value == "M")
				{
					discount = 0;
				}

				var totalInsurance = homeInsurance + autoInsurance
        		var optionals = additionalFlood + deductible
        		var discountAmount = discount * (totalInsurance + optionals)
        		var totalBill = (totalInsurance + optionals) - discountAmount

				totalPrice.value = totalInsurance.toFixed(2);
				totalOptionalItems.value = optionals.toFixed(2);
				totalDiscount.value = discountAmount.toFixed(2);
				totalAmount.value = totalBill.toFixed(2);
 
			'></button>

			<button onclick='
				auto.checked = false;
				home.checked = false;

				homeInsurance = 0;
        	 	autoInsurance = 0;
       			additionalFlood = 0;
        		deductible = 0;
        		discount = 0;
				
				totalInsurance = 0;
				optionals = 0;
				discountAmount = 0;
				totalBill = 0;

				homeType.value = "";
				floodInsurance.value = "";
				noDeductible.value = "";
				paymentType.value = "";
			
				totalPrice.value = "";
				totalOptionalItems.value = "";
				totalDiscount.value = "";
				totalAmount.value = "";

			'>Clear</button>
 	  	</p>
		
		<h2>Outputs</h2>
		<table>
			<tr>
				<th><h3>Item</h3></th>
				<th><h3>Price</h3></th>
			</tr>
			<tr>
				<td>Total Price</td>
				<td><input type="text" id="totalPrice" onchange=''></td>
			</tr>
			<tr>
				<td>Total Optional Items</td>
				<td><input type="text" id="totalOptionalItems" onchange=''></td>
			</tr>
			<tr>
				<td>Total Discount</td>
				<td><input type="text" id="totalDiscount" onchange=''></td>
			</tr>
			<tr>
				<td>Total Amount</td>
				<td><input type="text" id="totalAmount" onchange=''></td>
			</tr>
		</table>	
					
 	</body>
</html>
