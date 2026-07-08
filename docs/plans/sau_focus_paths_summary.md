# Saudi Arabia Focus Tree - Path Analysis

**Generated:** 2026-07-08  
**Total Mutually Exclusive Groups:** 29

---

## Major Path Choices (Must Pick One)

### 1. Border Dispute Resolution (Early Game)
**Choose one:**
- **SAU_solve_the_jafurah_dispute** - Diplomatic approach with UK
- **SAU_reject_the_riyadh_line** - Aggressive stance, claim territories

**Status:** ✓ Properly mutually exclusive

---

### 2. Oil Company Partnership (Early Game)
**Choose one of four:**
- **SAU_deal_with_bp** - British Petroleum partnership (requires diplomatic path)
- **SAU_invite_brabag** - German BRABAG partnership (requires aggressive path)
- **SAU_concessions_to_standard_oil** - American Standard Oil (either path)
- **SAU_2_Invite_the_Soviet_oil_barons** - Soviet partnership (requires aggressive path)

**Status:** ✓ All four properly mutually exclusive with each other

---

### 3. Political Ideology (Mid Game)
**Choose one of three:**
- **SAU_introduce_the_constitution** - Democratic path
  - Leads to democratization, western advisors, elections
- **SAU_continue_hakimovs_legacy** - Communist path
  - Leads to communist influence, Soviet alignment
- **SAU_seek_german_arms** - Fascist path
  - Leads to German equipment, axis alignment

**Status:** ✓ All three properly mutually exclusive with each other

---

### 4. International Alignment (Mid-Late Game)
**Choose one of four:**
- **SAU_western_alignment** - Join Allies
- **SAU_move_toward_german_alignment** - Join Axis
- **SAU_join_the_comintern** - Join Comintern
- **SAU_maintain_international_neutrality** - Stay neutral

**Status:** ✓ All four properly mutually exclusive with each other

---

### 5. Military Doctrine - Camelry vs Motorization (Army Branch)
**Choose one:**
- **SAU_incorporate_nomad_tactics** - Camelry focus, traditional warfare
- **SAU_motorization** - Motorized focus, modern warfare

**Status:** ✓ Properly mutually exclusive

---

### 6. Expansion Strategy (Mid Game)
**Choose one of three:**
- **SAU_ask_british_colonies** - Demand British colonies diplomatically
- **SAU_destabilize_the_east** - Create faction, regional subversion
- **SAU_abbasid_revolution** - Grand caliphate restoration path

**Status:** ⚠️ **ISSUE FOUND** - Only partial mutual exclusivity:
- SAU_ask_british_colonies excludes SAU_destabilize_the_east
- SAU_destabilize_the_east excludes SAU_ask_british_colonies AND SAU_abbasid_revolution
- **SAU_abbasid_revolution only excludes SAU_destabilize_the_east**

**Problem:** SAU_abbasid_revolution does NOT exclude SAU_ask_british_colonies, allowing both paths simultaneously!

---

### 7. Yemen/Oman Conquest Follow-up (Late Game)
**Choose one:**
- **SAU_establish_labor_camps** - Harsh occupation, more factories
- **SAU_autonomy_for_south_arabia** - Softer approach, less resistance

**Status:** ✓ Properly mutually exclusive

---

### 8. Oil Industry Control (Oil Branch)
**Choose one:**
- **SAU_nationalize_oil** - State control, independence
- **SAU_western_giants** - Foreign corporate partnership

**Status:** ✓ Properly mutually exclusive

---

### 9. Religious Approach (NEW - Religious Branch)
**Choose one:**
- **SAU_wahhabi_doctrine_export** - Conservative hard-line Islam
- **SAU_moderate_islam_approach** - Modern compatible Islam

**Status:** ✓ Properly mutually exclusive

---

### 10. Tribal Policy (NEW - Social Reform Branch)
**Choose one:**
- **SAU_sedentarization_incentives** - Force nomads to settle
- **SAU_preserve_nomadic_culture** - Honor Bedouin traditions

**Status:** ✓ Properly mutually exclusive

---

### 11. Conquest Integration (NEW - Consolidation Branch)
**Choose one:**
- **SAU_cultural_arabization** - Assimilation, Saudi identity
- **SAU_regional_autonomy_system** - Local self-governance

**Status:** ✓ Properly mutually exclusive

---

## Minor Mutually Exclusive Pairs

### 12. Abbasid Economic Policy
**Choose one:**
- **SAU_monetize** - Financial focus
- **SAU_steel_mill** - Industrial focus

**Status:** ✓ Properly mutually exclusive

---

## Path Summary

**Total Major Decision Points:** 11 main paths + 1 minor  
**Total Mutually Exclusive Groups:** 29 focus declarations

### Properly Exclusive Paths: 11 / 12
### Issues Found: 1

---

## CRITICAL ISSUE TO FIX

**SAU_abbasid_revolution** needs to exclude **SAU_ask_british_colonies** to complete the 3-way mutual exclusion in the expansion strategy group.

### Current State:
```
SAU_ask_british_colonies ↔ SAU_destabilize_the_east
SAU_destabilize_the_east ↔ SAU_abbasid_revolution
```

### Missing Link:
```
SAU_abbasid_revolution ↔ SAU_ask_british_colonies (NOT EXCLUDED!)
```

This allows players to take both the diplomatic colonial demand path AND the Abbasid caliphate restoration path simultaneously, which doesn't make thematic sense.

### Recommended Fix:
Add to SAU_abbasid_revolution's mutually_exclusive block:
```
mutually_exclusive = { 
    focus = SAU_destabilize_the_east 
    focus = SAU_ask_british_colonies
}
```

And add to SAU_ask_british_colonies:
```
mutually_exclusive = { 
    focus = SAU_destabilize_the_east
    focus = SAU_abbasid_revolution
}
```
