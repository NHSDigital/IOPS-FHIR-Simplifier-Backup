### Different Packs/Flavours

A dispenser may choose a mix of packs and flavours to satisfy a prescription and dispense them at the same time.

For example a prescriber may order.

| Medication ID (SNOMED) | Medication Name | Ordered Quantity |
|--
| 3542011000001100 | Generic Dioralyte Relief oral powder sachets sugar free | 40 sachet |

The dispenser chooses to issue 

| Medication ID (SNOMED) | Medication Name | Dispensed Quantity |
|--
| 3267611000001108 | Dioralyte Relief oral powder sachets apricot (Sanofi) 20 sachet| 20 sachet |
| 19826711000001103 | Dioralyte Relief oral powder sachets blackcurrant (Sanofi) 20 sachet | 20 sachet |

A `MedicationDispense` resource will be created for each medication dispensed and they will both be sent within the same `dispense-notification`.