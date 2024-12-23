## {{page-title}}

The order in which the structures within the Resource should be listed.

1. Medication Name
2. Medication Form (*if not implied within a VMP/AMP name*)
3. Trade Family Name (*if not implied within an AMP name*)

Then for each `dosageInstruction`;

4. method
5. doseAndRate.doseQuantity / .doseRange
6. doseAndRate.rateRatio / .rateQuantity / .rateRange
7. duration, durationMax
8. frequency, frequencyMax, period and periodMax
9. offset, when(s)
10. dayOfWeek(s)
11. timeOfDay(s)
12. route
13. site
14. asNeededCodeableConcept / asNeeded
15. boundsDuration / boundsRange
16. count, countMax
17. event(s)
18. maxDosePerPeriod / maxDosePerAdministration / maxDosePerLifetime
19. additionalInstruction(s)
20. patientInstruction

---