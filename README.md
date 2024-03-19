
#!/bin/bash

# Prompt user for input
read -p "Enter employee name: " name
read -p "Enter hours worked: " hours
read -p "Enter rate per hour: " rate

# Calculate basic pay
basic_pay=$(echo "$hours * $rate" | bc)

# Calculate tax based on basic pay
if [ $basic_pay -gt 70000 ]; then
    tax=$(echo "0.25 * $basic_pay" | bc)
elif [ $basic_pay -ge 15000 ]; then
    tax=$(echo "0.15 * $basic_pay" | bc)
else
    tax=0
fi

# Calculate net pay
net_pay=$(echo "$basic_pay - $tax" | bc)

# Display results
echo "Employee: $name"
echo "Basic Pay: $basic_pay"
echo "Tax: $tax"
echo "Net Pay: $net_pay"
<!---
Petermarigamageto/Petermarigamageto is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
