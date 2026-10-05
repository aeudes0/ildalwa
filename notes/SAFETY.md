# Laser Safety & Legal Compliance Guide

## General notice

This project (hardware schematics, firmware, and software implementation) is provided strictly for **educational and experimental purposes, in a controlled environment**. 

Operating lasers including those driven by DIY digital to analog converters (DACs) carries significant hazards:
* **Severe eye injuries & permanent blindness:** High-power laser beams (Class 3B and Class 4, ranging from 500 mW to several watts) cause instantaneous photochemical and thermal retinal destruction, both via **direct beam** exposure AND **diffuse reflections from glossy surfaces**.
* **Fire hazards:** Concentrated beams can ignite scenic materials such as back drops, plastics, and non-fire-rated fabrics instantly.
* **Optical sensor damage:** Projecting towards video projectors, digital cinema cameras, or smartphones can permanently burns their CMOS/CCD matrices.

The author and contributors of this repository decline all liability for physical injuries, equipment destruction, property damage, or legal sanctions resulting from the assembly, modification, or use of this device. Building and deploying this hardware implies that you accept full technical and legal responsibility for its operation.

---

## TL;DR: French Law

* **Classification:** Any laser above 500 mW is **Class 4** (the highest hazard category).
* **Legal possession:** Purchasing and holding a Class >2 laser is strictly restricted to authorized professional activities (entertainment/show business is an authorized use case under French law). This applies even if you can buy some on classic marketplaces.
* **Audience separation:** Beams must remain at least **3.00 meters above** the highest floor accessible to the audience and at least **2.50 meters laterally** away from any audience zone. Audience scanning without certified fail-safe scanning equipment is strictly prohibited.
* **Personnel qualification:** Operating a Class 3B or 4 laser in an "Establishment Receiving Public" (ERP) requires a certified Laser Safety Officer (**Agent de Sécurité Laser - ASL**).
* **Mandatory safety chain:** An emergency stop button (E-Stop) hardwired directly to the DB25 ILDA interlock loop (pins 4 and 17) is legally mandatory and must operate independently of software/firmware.

---

## French law

In France, the design, possession, and live public operation of stage lasers are strictly regulated across multiple legal codes:
### 1. Possession & Acquisition Restrictions
* **Loi n° 2011-267 (LOPPSI 2) & Décret n° 2012-1303:**
  The acquisition, detention, and use of lasers with an output class higher than **Class 2** (> 1 mW) are forbidden by default, **except** for specific listed professional usages. 
  * "Spectacle et affichage" (Live performance, entertainment, and light projection) is recognized as an authorized professional usage under Article 4 bis of the modified Decree 2007-665.
  * Illegally purchasing or using a Class 3R, 3B, or 4 laser outside authorized professional categories is punishable by up to 6 months imprisonment and a €7,500 fine.

### 2. Worker & Public Protection (Code du Travail)
* **Articles R. 4452-1 à R. 4452-31 du Code du travail (Directive européenne 2006/25/CE):**
  Defines exposure limits (Valeurs Limites d'Exposition - VLE / ELV) for artificial optical radiation:
  * Employers and production managers are legally required to perform an in-depth risk evaluation documented in the *Document Unique d'Évaluation des Risques* (DUER).
  * Preventive measures must ensure that technicians, performers, and crew members are never exposed beyond the Maximum Permissible Exposure (MPE / EMP).

### 3. Public Venue Regulations (ERP - Établissements Recevant du Public)
* **Règlement de sécurité contre les risques d'incendie et de panique dans les ERP (Arrêté du 25 juin 1980 modifié, dispositions applicables aux salles de spectacle de type L, CTS, etc.):**
  * **Volume de sécurité (Overhead Rule):** All active beams must travel at a minimum height of **3.00 meters** above the highest point of access for spectators (including mezzanines, tiered seating, standing pits). A lateral safety margin of **2.50 meters** must be maintained.
  * **Audience scanning:** Direct crowd projection with raw Class 4 lasers is treated as negligence under penal law unless validated by accredited safety measurement bodies (dosimetry tests, certified PASS hardware scan-failure units, and diverging optics).
  * **Physical shutter masking:** Mechanical masking flags (aluminum plates) must be screwed onto the fixture's aperture to physically prevent downward beam dispersion, guaranteeing protection even if the DAC, software, or galvanometers crash.
  * **Fire safety:** The projection area must not intersect stage backdrops, drapes, or decorations that are not certified fire retardant (Classement de réaction au feu M1 or Euroclasse B-s1, d0).

---

## Sources

* **Légifrance – Décret n° 2012-1303 du 26 novembre 2012 :** [Fixant la liste des usages spécifiques autorisés pour les appareils à laser sortant d'une classe supérieure à 2](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000026694613)
* **Légifrance – Code du travail :** [Articles R. 4452-1 à R. 4452-31 (Prévention des risques d'exposition aux rayonnements optiques artificiels)](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006072050/LEGISCTA000022432869/)
* **Norme NF EN 60825-1 (AFNOR / CENELEC):** *Sécurité des appareils à laser - Partie 1 : classification des matériels et exigences.*
* **Norme NF EN 60825-3 (AFNOR / CEI):** *Sécurité des appareils à laser - Partie 3 : Directives pour les affichages et spectacles laser.*
* **Directive Européenne 2006/25/CE :** *Prescriptions minimales de sécurité et de santé relatives à l'exposition des travailleurs aux rayonnements optiques artificiels.*

---

## Other legislations

If deploying or distributing this project outside France, local national guidelines must be consulted:

### United States (FDA / CDRH & ANSI)
* Regulated by the **Food and Drug Administration (FDA)** and the **Center for Devices and Radiological Health (CDRH)** under **21 CFR 1040.10 and 1040.11**.
* Introducing a Class 3B or Class 4 laser projector into interstate commerce or operating it in a public performance requires an approved **Laser Light Show Variance (Form FDA 3147)**.
* Safety boundaries follow **ANSI Z136.1** (*Safe Use of Lasers*) and **ANSI Z136.10** (*Safe Use of Lasers in Entertainment, Displays, and Exhibitions*). Minimum audience separation is **3.0 meters (10 ft)** vertically and **2.5 meters** laterally.

### Germany (DGUV)
* Governed by occupational health accident insurance regulations: **DGUV Vorschrift 11** (formerly BGV B2) and **DGUV Vorschrift 17** (Staging and Event Operations).
* Operating Class 3R, 3B, or 4 display lasers requires a certified **Laserschutzbeauftragter (LSB)** on site and prior written notification to the regional occupational safety authority (*Gewerbeaufsichtsamt*) and statutory accident insurer (*Berufsgenossenschaft*).