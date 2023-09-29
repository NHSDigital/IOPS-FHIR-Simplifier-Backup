## {{page-title}}

### Products (VMPs) where the VPI strength is expressed as an inaccurate decimal value

The vast majority of VMPs are defined with a Virtual Product Ingredient (VPI) strength as a whole number, e.g. numerator = 5 (mg) and denominator = 1 (ml). A small percentage of VMPs are defined with a numerator expressed as an incurate decimal value. 

Two examples are;

1. **Oxybutynin 5mg/15ml bladder irrigation vials**, VPI strength = 333.33 micrograms / 1 ml

2. **Methotrexate 25mg/3ml solution for injection pre-filled syringes**, VPI strength = 8.333 mg / 1 ml

This inaccuracy of values like `333.33` or `8.333` not being mathmetically the same as one third of a milligram means the mathematics used in these calculations does not result in a whole number. 

For example;

- VMP = `Oxybutynin 5mg/15ml bladder irrigation vials`
- Requested Dose = `10 milligram`
- Calculated Quantity = `2.002 vials`

and

- VMP = `Methotrexate 25mg/3ml solution for injection pre-filled syringes`
- Requested Dose = `25 milligram`
- Calculated Quantity = `1.041667 pre-filled disposable injection`

It would be unwise to add bespoke logic to round up to the nearest whole number in such cases as this would require an assumption that this is the intention of the prescriber.

A possible solution that will be discussed with the owners of the NHS dm+d would be to express the strength in a way that uses absolute values. 

For example;

1. **Oxybutynon 5mg/15ml bladder irrigation vials**, VPI strength = 1 mg / 3 ml
2. **Methotrexate 25mg/3ml solution for injection pre-filled syringes**, VPI strength = 25 mg / 3 ml

---
