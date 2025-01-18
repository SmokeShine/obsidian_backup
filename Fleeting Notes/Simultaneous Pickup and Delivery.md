202409051110
Status: #idea
Tags:

# Simultaneous Pickup and Delivery


### Example of Non-Obvious Capacity Violation

Consider a vehicle with a capacity of 10 units. Let’s say there are 3 customers:

1. **Customer A**: Delivery of 4 units, Pickup of 3 units.
2. **Customer B**: Delivery of 3 units, Pickup of 4 units.
3. **Customer C**: Delivery of 2 units, Pickup of 5 units.

Let’s examine a possible route sequence:

- Start with 10 units (full capacity).

#### Step 1: Visit Customer A

- **Deliver** 4 units → Load decreases to 6 units.
- **Pickup** 3 units → Load increases to 9 units.

So far, no capacity violation (still within the vehicle's capacity of 10).

#### Step 2: Visit Customer B

- **Deliver** 3 units → Load decreases to 6 units.
- **Pickup** 4 units → Load increases to 10 units.

Still no capacity violation.

#### Step 3: Visit Customer C

- **Deliver** 2 units → Load decreases to 8 units.
- **Pickup** 5 units → Load increases to 13 units.

Here, the total load after picking up at Customer C exceeds the vehicle’s capacity (13 units > 10 units). The violation only becomes apparent after visiting the last customer, even though no individual step previously indicated an issue.


Example 2

### Example of Non-Obvious Case: Pickup First, No Violation

Let’s consider a vehicle with a **capacity of 10 units**. The vehicle will visit three customers, with the following delivery and pickup demands:

1. **Customer A**: Pickup 4 units, Delivery 2 units.
2. **Customer B**: Pickup 2 units, Delivery 5 units.
3. **Customer C**: Pickup 1 unit, Delivery 4 units.

### Route Example: Pickup First, But No Violation

#### Step 1: Visit Customer A

- **Start with 0 units** on the vehicle (since it's starting empty).
- **Pickup** 4 units → Load increases to 4 units.
- **Deliver** 2 units → Load decreases to 2 units.

No violation here, the load never exceeds 4 units, and the vehicle is still far below its capacity of 10 units.

#### Step 2: Visit Customer B

- **Pickup** 2 units → Load increases to 4 units (2 + 2 = 4).
- **Deliver** 5 units → Load decreases to 0 units (the vehicle is now empty).

No violation occurs, despite the pickup being first, because after the delivery, the vehicle has ample space for future pickups.

#### Step 3: Visit Customer C

- **Pickup** 1 unit → Load increases to 1 unit.
- **Deliver** 4 units → Load decreases to 0 units.

No capacity violation occurs at any step of the route.


---
# References

1. 