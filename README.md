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
  DISPLAY "Enter bill amount: "
  READ billAmount

  WHILE billAmount <= 0 DO
    DISPLAY "Error: Bill amount must be a positive number."
    DISPLAY "Enter bill amount: "
    READ billAmount
  END WHILE

  DISPLAY "Enter service quality (poor, fair, good, excellent): "
  READ serviceQuality

  WHILE serviceQuality NOT IN ["poor", "fair", "good", "excellent"] DO
    DISPLAY "Error: Invalid service quality. Choose from (poor, fair, good, excellent)."
    DISPLAY "Enter service quality: "
    READ serviceQuality
  END WHILE

  DISPLAY "Enter number of people splitting the bill: "
  READ numPeople

  WHILE numPeople <= 0 OR numPeople IS NOT INTEGER DO
    DISPLAY "Error: Number of people must be a positive integer."
    DISPLAY "Enter number of people: "
    READ numPeople
  END WHILE

  DECLARE tipPercentage AS FLOAT
  IF serviceQuality = "poor" THEN
    tipPercentage = 0.10
  ELSE IF serviceQuality = "fair" THEN
    tipPercentage = 0.15
  ELSE IF serviceQuality = "good" THEN
    tipPercentage = 0.18
  ELSE IF serviceQuality = "excellent" THEN
    tipPercentage = 0.20
  END IF

  tipAmount = billAmount × tipPercentage
  totalAmount = billAmount + tipAmount
  amountPerPerson = totalAmount ÷ numPeople

  DISPLAY "Bill amount: $" + billAmount
  DISPLAY "Service quality: " + serviceQuality + " (" + (tipPercentage * 100) + "%)"
  DISPLAY "Tip amount: $" + tipAmount
  DISPLAY "Total amount: $" + totalAmount
  DISPLAY "Number of people: " + numPeople
  DISPLAY "Amount per person: $" + amountPerPerson
END
