# Saudi Arabia Focus Tree Expansion Plan

**Date:** 2026-07-08  
**Task:** Design and implement up to 50 new focuses for the Saudi Arabia focus tree  
**Hard constraint:** SAU_abbasid_revolution focus (x=10.75, y=11) must not be edited in content, effects, or logic. Only x/y coordinates may be adjusted if needed for layout.

---

## 1. Current Tree Analysis

### Existing Structure
The current Saudi Arabia focus tree has the following major branches:

1. **Opening Branch** (SAU_the_unifier → border dispute paths)
   - Jafurah dispute resolution (diplomatic vs aggressive)
   - Oil company choices (BP, BRABAG, Soviet, Standard Oil)
   - Early economic focuses

2. **Political Routes**
   - Democratic path (SAU_introduce_the_constitution)
   - Communist path (SAU_continue_hakimovs_legacy)
   - Fascist path (SAU_seek_german_arms)
   - Each leads to international alignment (Western, Comintern, Axis, Neutrality)

3. **Army Branch** (x=17-24, y=0-4)
   - Infantry, desert warfare, artillery
   - Camelry vs motorization split
   - Special forces and tank development

4. **Expansion/War Branch**
   - Regional conquest focuses (Yemen, Oman, Iran, Turkey)
   - British colony demands
   - Destabilization mechanics
   - "Our Rightful Domain" major expansion

5. **Oil/Industry Branch** (x=24.5-28, y=5-13)
   - Oil prospecting and pipeline development
   - Nationalization vs Western partnership split
   - Heavy industry development

6. **Abbasid Revolution Branch** (x=10.75, y=11-19)
   - Alternate grand expansion path
   - Mesopotamia campaign
   - Baghdad as new capital
   - Caliphate restoration mega-campaign

7. **Late Industrial Branch** (x=51-60, y=0-10)
   - Civilian development (left wing)
   - Military manufacturing (right wing)
   - Centered on SAU_industrial_foundation

8. **Miscellaneous Abbasid Support** (x=7.75-14.25, y=14-19)
   - Eastern/Western historical campaigns
   - House of Wisdom research slot
   - Mediterranean expansion

### Current Focus Count
Estimated ~180 focuses already in tree.

### Spacing Observations
- Main political tree uses y-spacing of 1-2 between layers
- Branch splits typically use x-spacing of 2-4 units
- The tree already extends from x=6 to x=60, y=0 to y=19

---

## 2. Design Goals

### What to Add
The expansion should focus on areas that feel underdeveloped or offer interesting new gameplay:

1. **Religious/Cultural Identity Branch**
   - Develop Saudi Arabia's role as guardian of holy sites
   - Balance traditional vs modernizing pressures
   - Ulema influence mechanics
   - Pilgrimage economy expansion beyond current SAU_enocurage_the_hajj

2. **Regional Diplomacy & Arab Unity**
   - Pan-Arabism vs Saudi nationalism
   - Regional league formation options (non-Abbasid paths)
   - Diplomatic integration of neighbors
   - Counter-colonial initiatives

3. **Internal Development & Reforms**
   - Tribal integration beyond current SAU_placate_the_tribes
   - Education and modernization programs
   - Administrative reforms
   - Women's rights and social reform debates

4. **Intelligence & Security Branch**
   - Internal security apparatus
   - Foreign intelligence gathering
   - Counter-espionage
   - Religious police mechanics

5. **Late-Game Consolidation**
   - Post-conquest integration mechanics
   - Stabilization after major expansion
   - Economic consolidation
   - Regional influence projection

### Branch Architecture

**Branch 1: Religious Authority & Cultural Identity** (x=32-38, y=2-10)
- Positioned to the right of existing army branch
- Explores Saudi Arabia's unique religious position
- Connects modernization with tradition
- Unlocks special decisions for Hajj management, religious diplomacy

**Branch 2: Pan-Arabism & Regional Diplomacy** (x=40-46, y=2-10)
- Positioned between religious branch and late industrial branch
- Offers non-Abbasid path to regional influence
- Creates diplomatic integration options
- League/bloc formation mechanics

**Branch 3: Internal Security & Intelligence** (x=32-38, y=12-16)
- Positioned below religious branch
- Connects to political paths
- Espionage and counter-espionage
- Internal stability mechanics

**Branch 4: Tribal Integration & Social Reform** (x=40-46, y=12-16)
- Positioned below diplomacy branch
- Deep dive into Saudi society
- Education and modernization
- Women's rights debates (sensitive, historical framing)

**Branch 5: Post-Expansion Consolidation** (x=15-20, y=17-19)
- Positioned near Abbasid late-game focuses
- Integration of conquered territories
- Administrative efficiency
- Cultural assimilation vs autonomy choices

---

## 3. Focus-by-Focus Design

### IMPORTANT: Prerequisite Syntax Clarification

**HOI4 Prerequisite Logic:**
- Single `prerequisite = { focus = A focus = B }` block → **OR logic** (either A or B satisfies)
- Multiple separate `prerequisite = { focus = A }` and `prerequisite = { focus = B }` blocks → **AND logic** (both A and B required)

**In this plan:**
- "Prerequisites: A OR B" → Single prerequisite block with both focuses (OR logic)
- "Prerequisites: A AND B" or "Prerequisites: A, B" → Two separate prerequisite blocks (AND logic)

### Branch 1: Religious Authority & Cultural Identity (15 focuses)

**SAU_guardians_of_the_holy_sites** (x=35, y=2, cost=5)
- Prerequisites: SAU_the_unifier (single prerequisite block)
- Icon: GFX_goal_generic_religious_focus or GFX_goal_PAL_jizya
- Reward: +0.05 stability, unlock religious decision category
- Description: Affirm Saudi role as protector of Mecca and Medina

**SAU_expand_hajj_infrastructure** (x=33, y=4, cost=8)
- Prerequisites: SAU_guardians_of_the_holy_sites (single prerequisite block)
- Icon: GFX_focus_generic_industry_2
- Reward: +2 infrastructure in state 856 (Mecca), +100 PP, unlock enhanced Hajj decisions
- Description: Build facilities to accommodate growing pilgrim numbers

**SAU_international_islamic_council** (x=37, y=4, cost=8)
- Prerequisites: SAU_guardians_of_the_holy_sites (single prerequisite block)
- Icon: GFX_goal_generic_intelligence_exchange
- Reward: Unlock decision to invite Muslim-majority countries to Islamic Council, diplomatic bonuses
- Description: Establish forum for Islamic world leadership

**SAU_wahhabi_doctrine_export** (x=33, y=6, cost=7)
- Prerequisites: SAU_expand_hajj_infrastructure (single prerequisite block)
- Mutually exclusive: SAU_moderate_islam_approach
- Icon: GFX_goal_PAL_declare_jihad
- Reward: +fascism support in Muslim states, unlock religious subversion decisions
- Description: Actively spread conservative Wahhabi interpretation abroad

**SAU_moderate_islam_approach** (x=37, y=6, cost=7)
- Prerequisites: SAU_international_islamic_council (single prerequisite block)
- Mutually exclusive: SAU_wahhabi_doctrine_export
- Icon: GFX_focus_generic_diplomatic_treaty
- Reward: Better relations with democracies, +stability
- Description: Present Saudi Islam as compatible with modern governance

**SAU_hajj_pilgrimage_economy** (x=35, y=7, cost=8)
- Prerequisites: SAU_wahhabi_doctrine_export OR SAU_moderate_islam_approach (single prerequisite block with OR logic)
- Icon: GFX_focus_generic_industry_3
- Reward: Special pilgrim economy idea (+consumer goods income, +PP gain)
- Description: Develop sophisticated economic system around annual Hajj

**SAU_religious_education_network** (x=33, y=9, cost=10)
- Prerequisites: SAU_hajj_pilgrimage_economy AND SAU_wahhabi_doctrine_export (two separate prerequisite blocks, both required)
- Icon: GFX_focus_generic_university_2
- Reward: +0.5 research bonus to religious tech (if exists), unlock madrasah decisions
- Description: Establish network of religious schools across Arabia

**SAU_islamic_finance_system** (x=37, y=9, cost=10)
- Prerequisites: SAU_hajj_pilgrimage_economy AND SAU_moderate_islam_approach (two separate prerequisite blocks, both required)
- Icon: GFX_goal_generic_financial_markets
- Reward: Special economic modifier, building cost reduction
- Description: Develop banking system compliant with Islamic law

**SAU_ulema_council_influence** (x=35, y=10, cost=8)
- Prerequisites: SAU_religious_education_network OR SAU_islamic_finance_system (single prerequisite block with OR logic)
- Icon: GFX_goal_generic_political_pressure
- Reward: Special Ulema Council idea (religious authority mechanic)
- Description: Formalize role of religious scholars in state governance

### Branch 2: Pan-Arabism & Regional Diplomacy (15 focuses)

**SAU_arab_unity_vision** (x=43, y=2, cost=5)
- Prerequisites: SAU_the_unifier (single prerequisite block)
- Icon: GFX_focus_IRQ_unite_mashriq
- Reward: +PP, unlock Arab Unity decision category
- Description: Articulate vision for unified Arab nation

**SAU_cairo_damascus_axis** (x=41, y=4, cost=8)
- Prerequisites: SAU_arab_unity_vision (single prerequisite block)
- Icon: GFX_goal_generic_intelligence_exchange
- Reward: Improved relations with Egypt, Syria; unlock diplomatic missions
- Description: Build alliance with other Arab power centers

**SAU_league_of_arab_states** (x=45, y=4, cost=8)
- Prerequisites: SAU_arab_unity_vision (single prerequisite block)
- Icon: GFX_focus_generic_diplomatic_treaty
- Reward: Unlock decision to form Arab League (faction), special league mechanics
- Description: Create formal organization for Arab cooperation

**SAU_arabic_language_promotion** (x=41, y=6, cost=7)
- Prerequisites: SAU_cairo_damascus_axis (single prerequisite block)
- Icon: GFX_focus_generic_diplomatic_treaty
- Reward: Cultural influence idea, +opinion with Arabic-speaking nations
- Description: Promote standardized Arabic as lingua franca

**SAU_anti_colonial_front** (x=43, y=6, cost=7)
- Prerequisites: SAU_cairo_damascus_axis AND SAU_league_of_arab_states (two separate prerequisite blocks, both required)
- Icon: GFX_goal_generic_attack_allies
- Reward: Unlock decisions to support independence movements
- Description: Coordinate opposition to European colonial presence

**SAU_economic_cooperation_council** (x=45, y=6, cost=7)
- Prerequisites: SAU_league_of_arab_states (single prerequisite block)
- Icon: GFX_goal_generic_positive_trade_relations
- Reward: Trade bonuses with Arab states, resource access decisions
- Description: Establish common market for member states

**SAU_joint_arab_military_command** (x=43, y=8, cost=10)
- Prerequisites: SAU_anti_colonial_front (single prerequisite block)
- Icon: GFX_goal_generic_allies_build_infantry
- Reward: Unlock volunteer force decisions, +XP when Arab states at war
- Description: Create unified command structure for Arab forces

**SAU_arab_cultural_renaissance** (x=41, y=8, cost=8)
- Prerequisites: SAU_arabic_language_promotion (single prerequisite block)
- Icon: GFX_focus_research
- Reward: Research bonus, +stability
- Description: Sponsor revival of classical Arab arts and sciences

**SAU_regional_infrastructure_fund** (x=45, y=8, cost=8)
- Prerequisites: SAU_economic_cooperation_council (single prerequisite block)
- Icon: GFX_goal_generic_construction
- Reward: PP gain, infrastructure in multiple states
- Description: Finance development projects across Arab world

**SAU_pan_arab_broadcasting** (x=43, y=10, cost=8)
- Prerequisites: SAU_joint_arab_military_command (single prerequisite block)
- Icon: GFX_goal_generic_propaganda
- Reward: Special propaganda idea, ideology drift in Arab states
- Description: Establish radio network promoting Arab unity

### Branch 3: Internal Security & Intelligence (10 focuses)

**SAU_establish_security_apparatus** (x=35, y=12, cost=7)
- Prerequisites: SAU_seek_german_arms OR SAU_introduce_the_constitution OR SAU_continue_hakimovs_legacy (single prerequisite block with OR logic - any one of three satisfies)
- Icon: GFX_focus_generic_military_mission
- Reward: Unlock intelligence agency upgrades, +PP
- Description: Create modern internal security service

**SAU_religious_police_force** (x=33, y=14, cost=5)
- Prerequisites: SAU_establish_security_apparatus (single prerequisite block)
- Icon: GFX_goal_generic_censorship
- Reward: +stability, -democratic support, special mutawwa idea
- Description: Empower religious police to enforce Islamic law

**SAU_foreign_intelligence_network** (x=37, y=14, cost=5)
- Prerequisites: SAU_establish_security_apparatus (single prerequisite block)
- Icon: GFX_goal_generic_intelligence_exchange
- Reward: Intelligence agency upgrades, operative slots
- Description: Develop capability to gather intelligence abroad

**SAU_counter_espionage_doctrine** (x=35, y=15, cost=8)
- Prerequisites: SAU_religious_police_force AND SAU_foreign_intelligence_network (two separate prerequisite blocks, both required)
- Icon: GFX_goal_generic_secret_weapon
- Reward: Counter-intelligence bonuses, reduced foreign influence
- Description: Train specialists in detecting enemy agents

**SAU_internal_passports** (x=33, y=16, cost=7)
- Prerequisites: SAU_counter_espionage_doctrine (single prerequisite block)
- Icon: GFX_focus_generic_diplomatic_treaty
- Reward: Resistance suppression bonus, -freedom modifier
- Description: Implement internal movement control system

**SAU_surveillance_state** (x=37, y=16, cost=7)
- Prerequisites: SAU_counter_espionage_doctrine (single prerequisite block)
- Icon: GFX_goal_generic_censorship
- Reward: Special surveillance idea, ideology drift resistance
- Description: Expand monitoring of population activities

### Branch 4: Tribal Integration & Social Reform (10 focuses)

**SAU_tribal_confederation_reforms** (x=43, y=12, cost=7)
- Prerequisites: SAU_liberalize_the_market OR SAU_placate_the_tribes (single prerequisite block with OR logic)
- Icon: GFX_focus_ETH_sway_the_warlords
- Reward: +manpower, tribal integration idea (stage 1)
- Description: Create formal structure for tribal participation

**SAU_sedentarization_incentives** (x=41, y=14, cost=8)
- Prerequisites: SAU_tribal_confederation_reforms (single prerequisite block)
- Mutually exclusive: SAU_preserve_nomadic_culture
- Icon: GFX_focus_generic_population_growth
- Reward: +building slots in desert states, -tribal unrest
- Description: Encourage nomads to adopt settled agricultural life

**SAU_preserve_nomadic_culture** (x=45, y=14, cost=8)
- Prerequisites: SAU_tribal_confederation_reforms (single prerequisite block)
- Mutually exclusive: SAU_sedentarization_incentives
- Icon: GFX_focus_ETH_keep_the_chitet
- Reward: Cavalry/camelry bonuses, tribal loyalty idea
- Description: Honor and maintain traditional Bedouin way of life

**SAU_universal_education_program** (x=43, y=15, cost=10)
- Prerequisites: SAU_sedentarization_incentives OR SAU_preserve_nomadic_culture (single prerequisite block with OR logic)
- Icon: GFX_focus_generic_university_2
- Reward: +research slot OR research bonus if already at cap
- Description: Establish schools throughout the kingdom

**SAU_womens_education_debate** (x=41, y=16, cost=8)
- Prerequisites: SAU_universal_education_program (single prerequisite block)
- Icon: GFX_goal_generic_political_pressure
- Reward: Stability hit, unlock follow-up decisions, social reform idea
- Description: Address controversial question of female schooling

**SAU_technical_colleges** (x=45, y=16, cost=8)
- Prerequisites: SAU_universal_education_program (single prerequisite block)
- Icon: GFX_focus_generic_industry_3
- Reward: +industrial research bonus, trained workforce idea
- Description: Create vocational training institutions

### Branch 5: Post-Expansion Consolidation (5 focuses)

**SPACING WARNING:** This branch sits close to existing Abbasid Support focuses (x=7.75-14.25, y=14-19). The leftmost consolidation focus at x=15 creates only a ~0.75 unit gap from the rightmost existing focus at x=14.25. **During implementation, verify that prerequisite lines between these branches do not create visual clutter or overlapping connections. If overlap occurs, shift this entire branch further right (e.g., x=18-23) to create adequate spacing.**

**SAU_administrative_integration** (x=17, y=17, cost=8)
- Prerequisites: SAU_integrate_the_levant OR SAU_our_rightful_domain (single prerequisite block with OR logic)
- Available: Control at least 15 states
- Icon: GFX_focus_generic_industry_1
- Reward: Compliance gain in non-core states, reduced resistance
- Description: Establish effective governance in conquered territories

**SAU_cultural_arabization** (x=15, y=18, cost=10)
- Prerequisites: SAU_administrative_integration (single prerequisite block)
- Mutually exclusive: SAU_regional_autonomy_system
- Icon: GFX_goal_generic_propaganda
- Reward: +compliance, ideology drift toward Saudi model
- Description: Promote Saudi Arabian identity in new territories

**SAU_regional_autonomy_system** (x=19, y=18, cost=10)
- Prerequisites: SAU_administrative_integration (single prerequisite block)
- Mutually exclusive: SAU_cultural_arabization
- Icon: GFX_goal_MPL_arabs_ministers
- Reward: Lower resistance, better stability, -manpower
- Description: Grant local self-governance within Saudi framework

**SAU_empire_administration** (x=17, y=19, cost=10)
- Prerequisites: SAU_cultural_arabization OR SAU_regional_autonomy_system (single prerequisite block with OR logic)
- Icon: GFX_goal_generic_major_alliance
- Reward: Major administrative efficiency idea, building bonuses
- Description: Create bureaucratic structure for managing vast realm

---

## 4. Integration Points

### Connections to Existing Tree
- Religious branch connects from SAU_the_unifier (early game)
- Diplomacy branch connects from SAU_the_unifier (early game)
- Security branch connects from political alignment focuses (mid game)
- Social reform branch connects from economic focuses (mid game)
- Consolidation branch connects from late expansion focuses (late game)

### SAU_abbasid_revolution Position
- Currently at x=10.75, y=11
- **Will remain at exactly these coordinates with zero content/logic changes**
- New consolidation branch (x=15-20, initially planned) may need adjustment
- **CRITICAL SPACING CHECK:** Consolidation branch sits very close to existing "Miscellaneous Abbasid Support" focuses at x=7.75-14.25, y=14-19. Only ~0.75 unit gap exists at the boundary (14.25 → 15). This may cause:
  - Overlapping prerequisite lines
  - Visual clutter when both branches are visible
  - Difficulty reading focus connections
- **SOLUTION:** During implementation, if overlap/clutter detected, shift consolidation branch further right (suggested: x=18-23 instead of x=15-20) to create minimum 3.75 unit gap for clarity
- No content, effect, or logic changes to SAU_abbasid_revolution focus itself

### Decision Category Unlocks
- Religious Authority → "SAU_religious_diplomacy" decision category
- Pan-Arabism → "SAU_arab_unity" decision category
- Internal Security → Intelligence operations, surveillance decisions
- Social Reform → Education, women's rights, tribal integration decisions
- Consolidation → Integration missions, resistance management

---

## 5. Reward Balance

### Factories & Buildings
Kept to minimum (already extensive in oil/industry branch):
- +2 infrastructure (Hajj expansion)
- Building cost modifiers in several focuses

### Research & XP
- 1 new research slot (universal education)
- Multiple research bonuses (religious, cultural, technical)
- Army/navy XP where thematic (joint command, intelligence)

### Political Power & Stability
- Distributed throughout as supporting rewards
- Larger grants tied to major route completions

### Ideas & Modifiers
- Religious authority mechanics (Ulema Council)
- Pilgrim economy bonuses
- Tribal integration stages
- Surveillance state mechanics
- Arab League mechanics
- Administrative efficiency for large empires

### Decisions & Mechanics
Primary reward type:
- Hajj management decisions
- Islamic diplomacy missions
- Arab League formation and management
- Independence movement support
- Integration and resistance management
- Social reform implementation

---

## 6. AI Behavior

### Weights
- AI should favor religious authority (factor 40-50) for Saudi flavor
- Pan-Arabism path if not going Abbasid (factor 30-40)
- Security apparatus always high priority (factor 60)
- Social reforms lower priority early game (factor 20-30)
- Consolidation unlocks automatically when conquest threshold met

### Route Conflicts
- Wahhabi export vs moderate Islam (historical: Wahhabi)
- Sedentarization vs nomadic preservation (historical: sedentarization)
- Arabization vs autonomy (depends on ideology and stability)

---

## 7. Localisation Tone

### Religious Branch
- Reverent tone for holy sites
- Authority and responsibility emphasis
- Traditional vs modern tension visible

### Diplomacy Branch
- Pan-Arab nationalism rhetoric
- Anti-colonial solidarity
- Brotherhood and unity themes

### Security Branch
- Order and stability emphasis
- Vigilance against threats
- Protection of the realm

### Social Reform Branch
- Progress and tradition balance
- Practical modernization
- Cautious on sensitive topics (women's rights historically appropriate)

### Consolidation Branch
- Imperial administration
- Burden of empire
- Integration challenges

---

## 8. Icon Requirements

Most focuses can use existing vanilla/R56 icons:
- Religious: GFX_goal_PAL_jizya, GFX_goal_PAL_declare_jihad
- Diplomacy: GFX_focus_IRQ_unite_mashriq, GFX_goal_generic_intelligence_exchange
- Security: GFX_goal_generic_censorship, GFX_goal_generic_secret_weapon
- Social: GFX_focus_generic_university_2, GFX_focus_generic_population_growth
- Industry: Standard construction icons

No new custom icons needed for initial implementation.

---

## 9. Implementation Order

1. Create Branch 1 (Religious Authority) - 15 focuses
2. Create Branch 2 (Pan-Arabism) - 15 focuses
3. Create Branch 3 (Internal Security) - 10 focuses
4. Create Branch 4 (Social Reform) - 10 focuses
5. Create Branch 5 (Consolidation) - 5 focuses

**Total: 55 focuses planned**

This slightly exceeds the 50-focus cap. During implementation, will evaluate:
- Merge some sequential focuses with similar themes
- Remove lowest-priority focuses from each branch
- Target exactly 50 or slightly under

---

## 10. Validation Checklist

After implementation, verify:
- [ ] All prerequisite chains are valid
- [ ] All prerequisite blocks use correct AND/OR logic as specified in plan
- [ ] No duplicate focus IDs
- [ ] No duplicate x,y coordinates
- [ ] SAU_abbasid_revolution unchanged (except x/y if needed)
- [ ] All focuses have icons assigned
- [ ] Mutually exclusive relationships properly defined
- [ ] AI weights present for major route choices
- [ ] No orphaned focuses (all connected to tree)
- [ ] Prerequisite lines don't cross excessively
- [ ] **Branch 5 spacing verified:** Check that consolidation branch (x=15-20 or adjusted x=18-23) does not create visual clutter with existing Abbasid Support branch (x=7.75-14.25). If overlap detected, shift consolidation branch further right.
- [ ] Total focus count ≤ 50 new focuses
- [ ] File syntax valid (test game load)
- [ ] Bracket matching correct
- [ ] All focus IDs referenced in prerequisites exist

---

## 11. Expected Gameplay Impact

### New Playstyles Enabled
1. **Religious diplomacy route**: Build Islamic coalition without Abbasid conquest
2. **Pan-Arab federalist**: Unite Arabs through diplomacy rather than force
3. **Modernizing autocrat**: Balance tradition with rapid social reform
4. **Surveillance state**: Focus on internal security and control
5. **Imperial administrator**: Master post-conquest integration challenges

### Existing Route Enrichment
- Abbasid path gains consolidation mechanics
- Western/Soviet alignment gains Arab diplomacy overlay
- Fascist path gains religious hard-line option
- Democratic path gains reform depth

### Player Choice Depth
Multiple meaningful branches added without making any single path mandatory. Tree should feel more complete without overwhelming the player.

---

**End of Plan**

**Next Step:** Await user approval before implementing focuses into `common/national_focus/saudi_arabia.txt`
