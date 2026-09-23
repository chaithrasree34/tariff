# Electricity Tariff Calculator
# Calculates electricity bill based on slab-wise consumption

def calculate_bill(units):
    if units <= 100:
        bill = units * 1.50
    elif units <= 200:
        bill = (100 * 1.50) + ((units - 100) * 2.50)
    elif units <= 500:
        bill = (100 * 1.50) + (100 * 2.50) + ((units - 200) * 4.00)
    else:
        bill = (100 * 1.50) + (100 * 2.50) + (300 * 4.00) + ((units - 500) * 6.00)

    fixed_charge = 50
    total_bill = bill + fixed_charge

    return bill, fixed_charge, total_bill


print("===================================")
print("     ELECTRICITY TARIFF CALCULATOR")
print("===================================")

units = float(input("Enter electricity units consumed: "))

if units < 0:
    print("Invalid input! Units cannot be negative.")
else:
    energy_charge, fixed_charge, total_bill = calculate_bill(units)

    print("\n--------- BILL DETAILS ---------")
    print(f"Units Consumed : {units:.2f} kWh")
    print(f"Energy Charge  : ₹{energy_charge:.2f}")
    print(f"Fixed Charge   : ₹{fixed_charge:.2f}")
    print("--------------------------------")
    print(f"Total Bill     : ₹{total_bill:.2f}")
    print("================================")