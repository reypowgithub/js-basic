# Lot Billing

## Story
BNI Parking Lot wants to keep their billing system simple. Every vehicle entering the parking lot gets their total duration (in hours) recorded when they leave. The billing system only needs two inputs:
- Vehicle Type
- Total Duration (in hours)

Your task is to create a program to calculate the total parking fee based on their pricing rules.

---

## Vehicle Types & Pricing

| Vehicle | First Hour | Next Hour (per hour) | Extra Charge if Duration > 24 Hours |
|---------|------------|----------------------|------------------------------------|
| Car     | Rp 5,000   | Rp 3,000            | Rp 50,000 (one-time only)         |
| Bike    | Rp 2,000   | Rp 1,000            | Rp 20,000 (one-time only)         |

---

## Input

| Name        | Type    | Description                       |
|-------------|---------|---------------------------------|
| VehicleType | String  | "car" or "bike"                 |
| Duration    | Integer | Total Parking Time in Hours     |

---

## Output

- Total Price in Rupiah

---

## Billing Rules

1. First hour uses "First Hour Price"
2. Every next hour uses "Next Hour Price"
3. If `Duration > 24 Hours` → Add Extra Charge (one time only)
4. If duration < 1 hour → still counted as 1 hour (round up)

---

## Example Cases

### Case 1

Input:
VehicleType: car 
Duration: 3

Calculation:
- First Hour = 5,000
- Next 2 Hours = 2 x 3,000 = 6,000  
Total = 5,000 + 6,000 = 11,000

---

### Case 2

Input:
VehicleType: bike 
Duration: 1


Calculation:
- First Hour = 2,000  
Total = 2,000

---

### Case 3

Input:
VehicleType: car 
Duration: 27


Calculation:
- First Hour = 5,000  
- Next 26 Hours = 26 x 3,000 = 78,000  
- Extra Charge = 50,000  
Total = 5,000 + 78,000 + 50,000 = 133,000


```javascript
let VehicleType 
let Duration 

function lotBillingSystem(VehicleType, Duration) {
    let firstHourPrice = 0
    let nextHourPrice = 0
    let extraCharge = 0

    switch (VehicleType) {
        case 'Car':
            firstHourPrice = 5000
            nextHourPrice = 3000
            extraCharge = 50000
            break;
        case 'Bike':
            firstHourPrice = 2000
            nextHourPrice = 1000
            extraCharge = 20000
            break;
        default:
            return "Invalid Vehicle Type"
    }

    let totalCost
    const oneDay = 24 
    if (Duration < 1) {
        totalCost = `Total Tagihan = ${firstHourPrice}`
    }else if (Duration < oneDay){
        totalCost = `Total Tagihan = ${firstHourPrice + (Math.floor(Duration - 1) * nextHourPrice)}`
    }
    else {
        totalCost = `Total Tagihan = ${firstHourPrice + (Math.floor(Duration - 1) * nextHourPrice + extraCharge)}`
    }

    return totalCost
}

console.log(lotBillingSystem('Car', 3))
console.log(lotBillingSystem('Bike', 1))
console.log(lotBillingSystem('Car', 27))
```
