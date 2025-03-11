# Tip Calculator Problem

## Objective
Create a program that calculates restaurant tips based on bill amount, service quality, and party size.

## Problem Description

When dining out, calculating the appropriate tip can sometimes be challenging, especially when splitting the bill among multiple people. Your task is to develop a program that helps users determine the tip amount and the total each person should pay.

### Requirements

#### Input
The program should prompt the user for:

1. The total bill amount (before tip)
2. The quality of service received (poor, fair, good, or excellent)
3. The number of people splitting the bill

#### Processing
The program should:

1 Determine the tip percentage based on service quality
  - Poor service: 10% tip
  - Fair service: 15% tip
  - Good service: 18% tip
  - Excellent service: 20% tip
    
2 Calculate the tip amount based on the bill and tip percentage\
3 Calculate the total amount (bill + tip)\
4 Calculate how much each person should pay (total ÷ number of people)

#### Output
The program should display:

1. The original bill amount
2. The service quality and corresponding tip percentage
3. The calculated tip amount
4. The total amount including tip
5. The number of people splitting the bill
6. The amount each person should pay

#### Error Handling
The program should:

1. Validate that the bill amount is a positive number
2. Ensure the service quality is one of the accepted ratings
3. Verify that the number of people is a positive integer
4. Provide appropriate error messages for invalid inputs

### Samples

```
Input:
Bill amount: $125.00
Service quality: good
Number of people: 5

Output:
Bill amount: $125.00
Service quality: good (18%)
Tip amount: $22.50
Total amount: $147.50
Number of people: 5
Amount per person: $29.50
```

```
Input:
Bill amount: $80.00
Service quality: excellent
Number of people: 2

Output:
Bill amount: $80.00
Service quality: excellent (20%)
Tip amount: $16.00
Total amount: $96.00
Number of people: 2
Amount per person: $48.00
```
START

# Step 1: Get inputs from the user
PRINT "Enter the total bill amount (before tip):"
READ bill_amount

PRINT "Enter the quality of service (poor, fair, good, excellent):"
READ service_quality

PRINT "Enter the number of people splitting the bill:"
READ num_people

# Step 2: Determine tip percentage based on service quality
IF service_quality = "poor" THEN
    tip_percentage = 10
ELSE IF service_quality = "fair" THEN
    tip_percentage = 15
ELSE IF service_quality = "good" THEN
    tip_percentage = 18
ELSE IF service_quality = "excellent" THEN
    tip_percentage = 20
ELSE
    PRINT "Invalid service quality. Defaulting to 15% tip."
    tip_percentage = 15

# Step 3: Calculate tip amount
tip_amount = (tip_percentage / 100) * bill_amount

# Step 4: Calculate total bill amount (including tip)
total_amount = bill_amount + tip_amount

# Step 5: Calculate amount per person
amount_per_person = total_amount / num_people

# Step 6: Display the results
PRINT "Tip Amount: ", tip_amount
PRINT "Total Bill Amount (including tip): ", total_amount
PRINT "Each person should pay: ", amount_per_person

END
