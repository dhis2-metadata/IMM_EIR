# Release Note { #imm-eir-release-note }


## 1.1.1
Minor update of Electronic Immunization Registry with 2.40 compatibility.

Improvements:
- Addition of Meningitis A vaccine to routine vaccination. First dose at 9-18 months, with contraindication for illness.
- Hepatitis B dose 2 and 3 to routine vaccination, with skip logic.


## 1.1.0

### Critical Bug Fixes

- Upgrade to version 2.36 compatibility
  - Required update on the “Unlock Immunization Schedule” rule
    - Unlock action no longer dependent on minimum number of characters in the unlock justification due to issue with “d2:length” variable in v2.36
- Fixed and standardized HIV+ contraindication program rules 
  - Change made to ProgramRuleVariable to use option code for HIV status

### Features Improvements

1. **Changes to program rule schedule for displaying all eligible doses at every visit**

   - Dose 1 now persists if you mark "no" the first time it is shown
   - Dose 2 is not an option until you have provided dose 1 (assuming you meet other age requirements)
   - Earlier version did not show doses that had been skipped in prior visit(s)

2. **Warning if user unlocks the vaccine schedule and provides response to a previously-provided dose**

3. **Revised the RV2 rule -- age must be after 15 months, and visit 4+ weeks after RV1**

4. **Rubella warning reinstated**

5. **IPV2-4 variables and data elements removed**

6. **Combined warnings for some contraindications if more than one “yes” is selected for the pre-immunization questions regarding HIV+, allergies, and current high temperature**

    - DHIS2 allows only one warning per data element. However for Measles (MCV) and Rotavirus (RV) there is a possibility of multiple contraindication warnings for each dose based on the pre-immunization questions
    - Measles Containing vaccine (MCV) warnings has 2 possible warnings that could be triggered based on the pre-immunization questions: HIV+ and allergy
        - HIV+ and not on ART: *“If the child is HIV+ and showing symptoms of severe immuno-suppression, postpone vaccination until stabilized with ART treatment"*
        - Allergy to Measles vaccine: *“it is contraindicated to give the measles vaccine if the child has had a previous severe allergic reaction to the vaccine.”*
        - If HIV+ and not on ART, plus allergy to Measles combines them: *“Postpone the measles vaccination until stabilized with ART treatment if the child is HIV+ and showing symptoms of severe immunosuppression. Note it is contraindicated to give the measles vaccine if the child has had a previous severe allergic reaction to the vaccine.”*
    - Rotavirus (RV) has 3 possible warnings that could be triggered based on the pre-immunization questions: HIV+, allergy, and current high temperature
        - If HIV+ and/or allergy is selected this warning will appear: *“It is contraindicated to give the Rotavirus vaccine if the child is HIV+ and not on ART and/or severely immuno-compromised, or if there was a previous severe allergic reaction”.*
        - If all 3 contraindications present (HIV+, allergy, and current high temperature) are selected for Rotavirus, the HIV+ and allergy warning supersedes the temperature warning.
        - The high temperature warning only displays if there is a high temperature, but the more restrictive contraindications are not entered. This warning will appear: *"Be aware, it is advisable to defer vaccination until after an acute infection and/or with temperature >39 degree C”*

    Example of combined warnings that appear based on the selected options for the pre-immunization questions:

    ![Example 1](resources/images/eir_tracker_35.png)

    ![Example 2](resources/images/eir_tracker_36.png)

7. **Vaccines Missing from the “Vaccine Card”**

    - The Tabular data entry view “vaccine card” is to contain all routine scheduled vaccines. Hep 1, IVP and Rubella were updated to show (display in reports) in the “vaccine card”

8. **Attributes**

     - Unique System Identifier (EPI)
     - National ID First name
     - Middle name
     - Surname
     - Date of birth*
     - Sex
     - Village/Neighbourhood
     - Home address
     - Primary contact's first name*
     - Primary contact's last name*
     - Primary contact's ID
     - Primary contact's number
     - Caregiver's first name
     - Caregiver's last name
     - Caregiver's ID
     - Caregiver's contact number
     - Photo

9. **Scheduled Override**
    - This screenshot highlights this text. *“The first time the entire immunization schedule is unlocked, the event date is recorded as a data element, and written to all subsequent events for the patient until opened again. In subsequent visits, the date of the schedule unlock is also shown in the top bar.”*

    ![Example 3](resources/images/eir_tracker_37.png)

## 1.0.0

Initial release of Electronic Immunization Registry package
