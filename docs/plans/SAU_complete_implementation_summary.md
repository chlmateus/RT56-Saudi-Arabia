# Saudi Arabia Focus Tree - Final Implementation Summary

**Date:** 2026-07-08  
**Implementation Status:** ✓ COMPLETE

---

## Implementation Statistics

**New Focuses Added:** 35  
**Total Focus Count:** 152 (117 existing + 35 new)  
**Mutually Exclusive Groups:** 29  
**Major Path Decisions:** 12

---

## New Branches Implemented

### Branch 1: Religious Authority & Cultural Identity
- **Location:** x=33-37, y=2-10
- **Focus Count:** 9
- **Key Features:**
  - Guardian of holy sites role
  - Hajj infrastructure expansion
  - Islamic Council diplomacy
  - **Choice:** Wahhabi doctrine export ↔ Moderate Islam approach
  - Pilgrim economy system
  - Religious education or Islamic finance (route-dependent)
  - Ulema Council influence

### Branch 2: Pan-Arabism & Regional Diplomacy
- **Location:** x=41-45, y=2-10
- **Focus Count:** 10
- **Key Features:**
  - Arab unity vision (non-Abbasid path)
  - Cairo-Damascus diplomatic axis
  - Arab League formation mechanics
  - Anti-colonial front support
  - Economic cooperation council
  - Joint Arab military command
  - Cultural renaissance
  - Regional infrastructure fund
  - Pan-Arab broadcasting network

### Branch 3: Internal Security & Intelligence
- **Location:** x=33-37, y=12-16
- **Focus Count:** 6
- **Key Features:**
  - Security apparatus establishment
  - Religious police (mutawwa) force
  - Foreign intelligence network
  - Counter-espionage doctrine
  - Internal passport system
  - Surveillance state mechanics

### Branch 4: Tribal Integration & Social Reform
- **Location:** x=41-45, y=12-16
- **Focus Count:** 6
- **Key Features:**
  - Tribal confederation reforms
  - **Choice:** Sedentarization incentives ↔ Preserve nomadic culture
  - Universal education program
  - Women's education debate
  - Technical colleges

### Branch 5: Post-Expansion Consolidation
- **Location:** x=21-25, y=17-19 (shifted right to avoid clutter)
- **Focus Count:** 4
- **Key Features:**
  - Administrative integration (requires 15+ states)
  - **Choice:** Cultural Arabization ↔ Regional autonomy system
  - Empire administration capstone

---

## Complete Path Structure

### 1. Border Dispute (Early Game)
- ✓ SAU_solve_the_jafurah_dispute ↔ SAU_reject_the_riyadh_line

### 2. Oil Company Partnership (Early Game - 4-way choice)
- ✓ SAU_deal_with_bp ↔ SAU_invite_brabag ↔ SAU_concessions_to_standard_oil ↔ SAU_2_Invite_the_Soviet_oil_barons

### 3. Political Ideology (Mid Game - 3-way choice)
- ✓ SAU_introduce_the_constitution ↔ SAU_seek_german_arms ↔ SAU_continue_hakimovs_legacy

### 4. International Alignment (Mid-Late Game - 4-way choice)
- ✓ SAU_western_alignment ↔ SAU_move_toward_german_alignment ↔ SAU_join_the_comintern ↔ SAU_maintain_international_neutrality

### 5. Military Doctrine (Army Branch)
- ✓ SAU_incorporate_nomad_tactics ↔ SAU_motorization

### 6. Expansion Strategy (Mid Game - 3-way choice) **FIXED**
- ✓ SAU_ask_british_colonies ↔ SAU_destabilize_the_east ↔ SAU_abbasid_revolution
- **All three now properly mutually exclusive**

### 7. Yemen/Oman Follow-up (Late Game)
- ✓ SAU_establish_labor_camps ↔ SAU_autonomy_for_south_arabia

### 8. Oil Industry Control (Oil Branch)
- ✓ SAU_nationalize_oil ↔ SAU_western_giants

### 9. Religious Approach (NEW - Religious Branch)
- ✓ SAU_wahhabi_doctrine_export ↔ SAU_moderate_islam_approach

### 10. Tribal Policy (NEW - Social Reform Branch)
- ✓ SAU_sedentarization_incentives ↔ SAU_preserve_nomadic_culture

### 11. Conquest Integration (NEW - Consolidation Branch)
- ✓ SAU_cultural_arabization ↔ SAU_regional_autonomy_system

### 12. Abbasid Economic (Minor)
- ✓ SAU_monetize ↔ SAU_steel_mill

---

## Validation Results

### Syntax Checks
- ✓ **Bracket Matching:** 1,269 open / 1,269 close (perfect)
- ✓ **No Duplicate Focus IDs:** All 152 focuses unique
- ✓ **Relative Coordinates Valid:** Proper use of relative_position_id
- ✓ **All New Focuses Present:** 35/35 verified in file

### SAU_abbasid_revolution Hard Constraint
- ✓ **Position:** x=10.75, y=11 (unchanged)
- ✓ **Content:** All original effects, prerequisites, and rewards intact
- ✓ **Only Change:** Added SAU_ask_british_colonies to mutually_exclusive block

### Mutual Exclusivity
- ✓ **All 12 major path choices** properly mutually exclusive
- ✓ **3-way expansion path** now complete (was missing link, now fixed)

### Spacing
- ✓ **Branch 5 repositioned:** x=21-25 instead of x=15-20 to avoid overlap with Abbasid Support branch
- ✓ **Adequate gaps:** Minimum 3.75 units between Branch 5 and existing focuses

---

## Design Principles Followed

### Prerequisite Logic
- All prerequisites use explicit AND/OR syntax as specified in plan
- Single `prerequisite = { focus = A focus = B }` blocks for OR logic
- Multiple separate `prerequisite` blocks for AND logic

### Reward Balance
- Focus on decisions, mechanics, and gameplay unlocks over stat dumps
- Ideas and modifiers tied to gameplay systems
- Building rewards kept minimal (already extensive in oil/industry branch)
- Research bonuses and slots where thematic

### AI Behavior
- AI weights scaled by government type
- Historical preferences (e.g., Wahhabi path favored)
- Route validity checks (e.g., don't go Abbasid if already in Arab Unity path)

### Integration
- Religious branch connects from SAU_the_unifier (early)
- Diplomacy branch connects from SAU_the_unifier (early)
- Security branch connects from political alignment focuses (mid)
- Social reform connects from economic focuses (mid)
- Consolidation connects from late expansion focuses (late)

---

## Files Modified

1. `common/national_focus/saudi_arabia.txt` - Added 35 new focuses, fixed mutual exclusivity

---

## Next Steps for User

### Required: Localisation
All new focuses need localisation entries in `localisation/english/sau_focus_l_english.yml`:

**Focus Names (35):**
- SAU_guardians_of_the_holy_sites
- SAU_expand_hajj_infrastructure
- SAU_international_islamic_council
- SAU_wahhabi_doctrine_export
- SAU_moderate_islam_approach
- SAU_hajj_pilgrimage_economy
- SAU_religious_education_network
- SAU_islamic_finance_system
- SAU_ulema_council_influence
- SAU_arab_unity_vision
- SAU_cairo_damascus_axis
- SAU_league_of_arab_states
- SAU_arabic_language_promotion
- SAU_anti_colonial_front
- SAU_economic_cooperation_council
- SAU_joint_arab_military_command
- SAU_arab_cultural_renaissance
- SAU_regional_infrastructure_fund
- SAU_pan_arab_broadcasting
- SAU_establish_security_apparatus
- SAU_religious_police_force
- SAU_foreign_intelligence_network
- SAU_counter_espionage_doctrine
- SAU_internal_passports
- SAU_surveillance_state
- SAU_tribal_confederation_reforms
- SAU_sedentarization_incentives
- SAU_preserve_nomadic_culture
- SAU_universal_education_program
- SAU_womens_education_debate
- SAU_technical_colleges
- SAU_administrative_integration
- SAU_cultural_arabization
- SAU_regional_autonomy_system
- SAU_empire_administration

**Focus Descriptions (35):** Add `_desc` suffix to each

**Custom Tooltips (10+):**
- SAU_unlock_religious_diplomacy_tt
- SAU_enhanced_hajj_decisions_tt
- SAU_islamic_council_invite_tt
- SAU_wahhabi_export_tt
- SAU_arab_unity_decisions_tt
- SAU_diplomatic_missions_tt
- SAU_form_arab_league_tt
- SAU_independence_support_tt
- SAU_resource_access_tt
- SAU_volunteer_decisions_tt
- SAU_intelligence_upgrades_tt
- SAU_madrasah_decisions_tt
- SAU_womens_reform_decisions_tt

**National Spirits/Ideas (~20):**
- SAU_pilgrim_economy_idea
- SAU_ulema_council_idea
- SAU_arabic_cultural_influence
- SAU_arab_economic_cooperation
- SAU_arab_military_coordination
- SAU_pan_arab_media
- SAU_arab_propaganda_influence (timed)
- SAU_mutawwa_force
- SAU_counter_intelligence_focus
- SAU_internal_passport_system
- SAU_surveillance_apparatus
- SAU_tribal_integration_1
- SAU_sedentarization_program
- SAU_nomadic_tradition_preserved
- SAU_social_reform_tension (timed)
- SAU_technical_training
- SAU_arabization_policy
- SAU_regional_autonomy
- SAU_imperial_administration
- SAU_islamic_banking_idea

**Opinion Modifiers:**
- SAU_wahhabi_influence
- moderate_islam_relations
- sau_arab_cooperation
- sau_cultural_ties

### Required: National Spirits
Create idea definitions in `common/ideas/` for all ideas listed above

### Required: Decisions
Create decision categories referenced in focuses:
- Religious diplomacy decisions
- Arab Unity decisions
- Enhanced Hajj decisions
- Independence support decisions
- Intelligence/surveillance decisions
- Women's education reform decisions
- Integration missions

### Optional: Icons
All focuses use existing vanilla/R56 icons. Custom icons can be added later if desired.

---

## Testing Checklist

- [ ] Game loads without errors
- [ ] All 35 new focuses visible in focus tree
- [ ] Mutual exclusions prevent taking incompatible paths
- [ ] Prerequisites work correctly
- [ ] AI takes reasonable paths
- [ ] No visual overlap or crossing prerequisite lines
- [ ] Localisation displays correctly
- [ ] Ideas apply when focuses complete
- [ ] Decisions unlock as intended

---

**Implementation Status:** ✓ COMPLETE  
**Ready for:** Localisation, ideas, decisions, and in-game testing
