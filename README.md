# Shipping Cost Calculator (Java)

This project implements a **shipping-cost calculator** for a delivery service using **object-oriented programming in Java**. It was developed as part of **COE318 – Digital Systems (Lab 6)** and focuses on **inheritance, method overriding, validation, and cost computation logic**.

The system models different parcel types with varying pricing rules and prints their calculated shipping costs.

---

## Objectives

- Implement a class hierarchy using inheritance
- Override methods to extend base behavior
- Validate constructor arguments
- Compute shipping costs using layered pricing logic
- Demonstrate polymorphism through a shared interface

---

## Project Overview

The application calculates shipping costs for parcels based on:
- Weight
- Travel distance
- Optional insurance
- Parcel-specific surcharges

Different parcel types extend a common base class and add their own pricing rules.

---

## Class Structure

### `Parcel` (Superclass)
Represents a basic parcel with:
- Weight
- Distance
- Optional insurance

**Key features:**
- Validates input (positive weight, non-negative distance)
- Calculates base shipping cost
- Applies insurance fee (maximum of $1.50 or 2% of total)

This class provides the foundation for all other parcel types.

---

### `StandardParcel` (extends `Parcel`)
Adds a **size tier**:
- `S` (Small)
- `M` (Medium)
- `L` (Large)

**Additional cost:**
- Small: +$0.75  
- Medium: +$1.25  
- Large: +$1.75  

The shipping cost builds on the base cost from `Parcel`.

---

### `ExpressParcel` (extends `StandardParcel`)
Represents expedited delivery.

**Additional cost logic:**
- Increases standard cost by **35%**
- Adds a **$7.50 flat fee** for same-day delivery (if selected)

---

### `InternationalParcel` (extends `Parcel`)
Represents cross-border shipments.

**Additional fields:**
- Destination region (e.g., EU, APAC)
- Customs rate (0.0–0.25)

**Additional cost logic:**
- Fixed international handling fee: **$8.00**
- Customs duty: `customsRate × base cost`

---

### `Main`
Creates sample parcel objects and prints their calculated shipping costs.

---

## Expected Output

Running `Main.java` produces:

Cost: $14.65
Cost: $17.56
Cost: $62.70

----

## Key Concepts Demonstrated

- Inheritance and polymorphism
- Constructor validation using exceptions
- Layered cost calculation
- Code reuse via superclass methods
- Real-world modeling using OOP

---
Developed as part of COE318 – Digital Systems coursework.
