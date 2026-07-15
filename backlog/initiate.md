Da. Mislim celo, da je po vseh iteracijah nastalo dovolj informacij, da se da opisati precej stabilno **referenčno arhitekturo FactForge**. Ne bi je imel za dokončno, ampak ocenjujem, da je približno **80–90 % konceptualne arhitekture** že oblikovane.

Opazil pa sem še nekaj pomembnega: projekt se je med razpravo dejansko spremenil.

Na začetku je bil:

> **AI sistem za avtomatizirano pisanje kakovostnih blog člankov.**

Danes pa ga jaz vidim kot:

> **Evidence-first publishing platform za pripravo decision intelligence vsebin.**

To ni samo drugačno poimenovanje, ampak drugačna arhitektura.

---

# Referenčna sistemska arhitektura FactForge

```text
                        USER
                          │
                          ▼
                  Topic Definition
                  (Topic Registry)
                          │
                          ▼
                Research Orchestrator
                          │
        ┌─────────────────┴──────────────────┐
        ▼                                    ▼
  Source Discovery                  Corpus Quality Analysis
        │                                    │
        └─────────────────┬──────────────────┘
                          ▼
                    Research Corpus
                          │
                          ▼
                 Evidence Extraction
                          │
                          ▼
                  Claim Construction
                          │
                 (interpretation layer)
                          ▼
         ┌────────────────┴─────────────────┐
         ▼                                  ▼
    Claim Registry                 Ambiguity Registry
         │                                  │
         └────────────────┬─────────────────┘
                          ▼
                 Editorial Review Gate
                          │
         ┌────────────────┴───────────────────┐
         ▼                                    ▼
     Approved Claims                 Approved Ambiguities
                          │
                          ▼
                 Publishing Engine
         ┌────────────┬─────────────┬──────────────┐
         ▼            ▼             ▼              ▼
      Article     Reality Check  Decision Brief  Topic Page
         │            │             │              │
         └────────────┴─────────────┴──────────────┘
                          ▼
                 Markdown + YAML
                          ▼
                    MDX Enrichment
                          ▼
              JSON-LD + Astro Static Site
                          ▼
                    Published Library

Future:
Entity Registry
Knowledge Graph
Semantic Search
```

---

# Posamezni sloji

## 1. Topic Registry

To je vhod v sistem.

Ne vsebuje še članka.

Definira:

* temo,
* ciljno publiko,
* namen,
* časovni horizont,
* tip odločitve.

Primer:

> "Ali naj proizvodno podjetje uvede AI agente v podporne procese?"

To ni naslov članka.

To je raziskovalno vprašanje.

---

## 2. Research Layer

To je po mojem eden najpomembnejših delov sistema.

Njegova naloga ni zbiranje "dobrih člankov".

Njegova naloga je sestaviti čim bolj reprezentativen korpus.

Vključuje:

* primarne vire,
* akademske raziskave,
* regulatorje,
* industrijske analize,
* vendorje,
* kritične oziroma nasprotne vire.

Output ni članek.

Output je:

```text
Research Corpus
```

---

## 3. Evidence Layer

To je srce FactForge.

Vendar ne vsebuje resnice.

Vsebuje:

> interpretacije posameznih dokazov.

Najpomembnejši objekt:

```text
Claim
```

Vsak claim ima:

* statement,
* scope,
* evidence,
* source excerpt,
* status,
* review lifecycle.

---

## 4. Ambiguity Layer

To je največja diferenciacija projekta.

Namesto:

```text
Facts only
```

FactForge hrani:

```text
Facts

+

Structured uncertainty
```

Sem sodijo:

* konflikti med raziskavami,
* različne šole mišljenja,
* različni pogoji veljavnosti,
* odprta vprašanja.

To po mojem naredi sistem precej bolj uporaben za odločevalce.

---

## 5. Editorial Governance

To ni AI komponenta.

To je poslovna komponenta.

Tu človek potrjuje:

* claim-e,
* ambiguity-je,
* ključne zaključke,
* priporočila.

Ne potrjuje zgolj slovnice članka.

Potrjuje epistemološko kakovost.

---

## 6. Publishing Layer

To ni generator besedila.

To je generator pogledov.

Iz istih claim-ov nastane:

* članek,
* Reality Check,
* Decision Brief,
* kasneje Topic Page.

To pomeni, da se isti pregledani claim uporablja večkrat.

To je glavni vir skalabilnosti.

---

## 7. Presentation Layer

Markdown ostane kanonični format.

YAML vsebuje:

* metapodatke,
* povezave,
* revizijske informacije.

MDX dodaja:

* TL;DR,
* Reality Check,
* Evidence Table,
* Decision Brief,
* interaktivne komponente.

Astro generira:

* statične strani,
* JSON-LD,
* sitemap,
* RSS,
* AI-SEO prijazen HTML.

---

# Temeljna načela sistema

Po vseh iteracijah bi jih zapisal takole.

### 1. Evidence before prose

Najprej nastanejo dokazi.

Besedilo pride šele nato.

---

### 2. Claims are interpretations

Claim ni resnica.

Je preverljiva interpretacija dokazov.

---

### 3. Preserve uncertainty

Negotovosti ne skrivamo.

Strukturiramo jih.

---

### 4. Reuse reviewed knowledge

Pregledani claim se uporabi večkrat.

Ne preverjamo vsakega članka od začetka.

---

### 5. Decision support, not truth declaration

FactForge ne razglaša resnice.

Pomaga razumeti:

* kaj vemo,
* česa ne vemo,
* zakaj se stroka ne strinja,
* katere predpostavke vodijo do različnih zaključkov.

---

# Po mojem mnenju manjka še en pomemben podsistem

Če bi nadaljeval razvoj arhitekture, bi naslednji dokument posvetil samo enemu delu:

## Evidence Lifecycle & Governance

To bi opisovalo:

* kako nastane claim,
* kako se spreminja,
* kako se razcepi,
* kako se združi,
* kako postane contested,
* kako ga nov dokaz nadomesti,
* kako se propagirajo spremembe v vse članke, Reality Checke in Decision Briefe, ki ta claim uporabljajo.

Po mojem je to zadnji večji manjkajoči gradnik. Ko bo definiran ta življenjski cikel, bo arhitektura FactForge prvič predstavljala koherenten sistem, ne le zbirko zelo dobrih idej.


---


Da. Evidence lifecycle & governance bi dodal kot **horizontalni nadzorni sloj**, ki ne stoji samo med Evidence Layerjem in Publishing Layerjem, ampak upravlja celoten življenjski cikel virov, dokazov, claimov, ambiguity objektov in priporočil.

## Posodobljena arhitektura

```text
Topic Definition
      ↓
Research Orchestrator
      ↓
Source Discovery
      ↓
Research Corpus
      ↓
Evidence Extraction
      ↓
Claim Construction
      ↓
Claim Registry ───────────────┐
      ↓                       │
Ambiguity Registry            │
      ↓                       │
Editorial Review Gate         │
      ↓                       │
Approved Knowledge            │
      ↓                       │
Publishing Views              │
      ↓                       │
Article / Reality Check /     │
Decision Brief / Topic Page   │
                              │
══════════════════════════════╪════════════════════
 EVIDENCE LIFECYCLE &         │
 GOVERNANCE CONTROL PLANE     │
══════════════════════════════╪════════════════════
                              │
 Source monitoring            │
 Freshness rules              │
 Contradiction detection      │
 Change impact analysis       │
 Review queues                │
 Versioning                   │
 Approval history             │
 Retraction / supersession    │
 Publication propagation ─────┘
```

Ta sloj je nekakšen **control plane** FactForge. Vsebinski sloji hranijo znanje; governance sloj določa, ali je to znanje še veljavno, kdo ga je odobril in kaj se mora zgoditi, ko pride nov dokaz.

# 1. Ločeni življenjski cikli

Ne bi imel enega skupnega statusa za vse objekte. Source, evidence, claim, ambiguity in recommendation imajo različne življenjske cikle.

## Source lifecycle

```text
discovered
→ screened
→ accepted
→ monitored
→ outdated
→ unavailable
→ archived
```

Primer:

* `discovered`: vir je najden, vendar še ni ocenjen;
* `screened`: preverjena je relevantnost in identiteta vira;
* `accepted`: lahko se uporablja kot dokaz;
* `outdated`: še obstaja, vendar so podatki zastareli;
* `unavailable`: URL ne deluje ali je vsebina umaknjena;
* `archived`: ne uporablja se več za aktualne trditve.

## Evidence lifecycle

Evidence je konkreten izvleček ali rezultat iz vira.

```text
extracted
→ verified
→ accepted
→ challenged
→ superseded
→ retired
```

Pomembno: source in evidence nista isto. En zanesljiv vir lahko vsebuje napačno interpretiran ali nerelevanten izvleček.

## Claim lifecycle

```text
draft
→ in_review
→ approved
→ active
→ contested
→ superseded
→ retired
```

Pomen statusov:

* `draft`: agent je claim ustvaril;
* `in_review`: čaka na človeka;
* `approved`: prestal je epistemološki pregled;
* `active`: lahko napaja objavljene vsebine;
* `contested`: nov dokaz mu relevantno nasprotuje;
* `superseded`: nadomestil ga je natančnejši claim;
* `retired`: ni več aktualen ali uporaben.

## Ambiguity lifecycle

```text
open
→ structured
→ reviewed
→ published
→ narrowed
→ resolved
→ reopened
```

Ambiguity ne postane nujno “resolved”. Pogosto se samo zoži ali spremeni.

## Recommendation lifecycle

```text
draft
→ assumption_review
→ approved
→ published
→ invalidated
→ retired
```

Recommendation mora imeti strožji gate kot navaden claim, ker je normativna sodba.

# 2. Osrednji governance objekti

V sistem bi dodal vsaj štiri nove registre.

## Review Registry

Hrani vse človeške odločitve:

```yaml
review_id: review_2026_0042
object_type: claim
object_id: claim_ai_roi_017
reviewer: editor_01
decision: approved
rationale: >
  Claim is narrowly scoped and supported by two independent comparative studies.
reviewed_at: 2026-07-15
```

To omogoča audit trail.

## Change Event Registry

Vsaka pomembna sprememba mora biti dogodek:

```yaml
event_type: claim_contested
claim_id: claim_ai_roi_017
trigger_source: source_2026_119
detected_at: 2026-07-15
reason: >
  New study reports no measurable productivity improvement under comparable conditions.
```

## Dependency Registry

Mora biti znano, katere objave uporabljajo kateri claim.

```yaml
claim_id: claim_ai_roi_017
used_by:
  - article_ai_agents_roi
  - topic_ai_agents
  - decision_brief_cto_ai_agents
```

To je nujno za propagacijo sprememb.

## Policy Registry

Pravila ne smejo biti zakopana v promptih.

Primer:

```yaml
policy_id: contested_claim_publication
rule: >
  A contested claim may remain visible only if opposing evidence and the contested status
  are shown in the published view.
```

# 3. Dve vrsti sprožilcev

Lifecycle ne sme temeljiti samo na datumu.

## Časovni sprožilci

```yaml
last_reviewed: 2026-07-15
review_after: 2026-10-15
stale_after: 2027-01-15
```

Primerno za:

* tržne podatke,
* regulatorne spremembe,
* hitro spreminjajoče se tehnologije,
* cene,
* adoption metrike.

## Dogodkovni sprožilci

Primeri:

* nov vir nasprotuje aktivnemu claimu;
* regulator objavi novo pravilo;
* vir je umaknjen;
* metodologija študije je diskreditirana;
* claim začne uporabljati nova publikacija;
* scope claim-a se spremeni;
* priporočilo izgubi eno od ključnih predpostavk.

Dogodkovni trigger je pogosto pomembnejši od `review_after`.

# 4. Contradiction handling

Ko sistem najde nov dokaz, ki nasprotuje claimu, ne sme takoj spreminjati javne vsebine.

Predlagani tok:

```text
New source
   ↓
Evidence extracted
   ↓
Potential contradiction detected
   ↓
Claim status → contested
   ↓
Impact analysis
   ↓
Human review
   ↓
One of:
- claim remains active
- claim scope is narrowed
- claim is split
- claim becomes ambiguity
- claim is superseded
- claim is retired
```

To je pomembno, ker novo nasprotovanje ni nujno prava kontradikcija. Lahko gre za:

* drugačen scope,
* drugo populacijo,
* drugo časovno obdobje,
* drugo definicijo,
* slabšo metodologijo.

# 5. Impact propagation

Ko se claim spremeni, mora sistem ugotoviti, kaj vse je prizadeto.

Primer:

```text
claim_ai_roi_017 → contested
```

Sistem naj vrne:

```text
Affected:
- 2 published articles
- 1 Reality Check
- 1 Decision Brief
- 1 topic page
- 3 JSON-LD summaries
```

Nato določi akcijo:

| Vpliv                      | Akcija                            |
| -------------------------- | --------------------------------- |
| manjša formulacija         | avtomatski predlog popravka       |
| sprememba scope-a          | obvezen uredniški pregled         |
| claim postane contested    | opozorilo na vseh javnih pogledih |
| claim retired              | odstranitev ali nadomestitev      |
| priporočilo izgubi podporo | takojšen umik priporočila         |

# 6. Human governance gates

Predlagal bi tri stopnje pregleda.

## Gate 1 — Evidence acceptance

Človek preveri:

* ali izvleček res podpira interpretacijo;
* ali je context preserved;
* ali je scope pravilen.

## Gate 2 — Claim approval

Človek preveri:

* atomarnost;
* falsifikabilnost;
* anti-trivialnost;
* terminološko skladnost;
* supporting in opposing evidence.

## Gate 3 — Publication judgement

Človek preveri:

* Reality Check;
* ambiguity framing;
* Decision Brief;
* priporočila in predpostavke.

Ne potrebuje vsak claim vseh treh gateov. Priporočila in sporne teme pa jih potrebujejo.

# 7. Risk-based governance

Vsi claimi ne potrebujejo enake strogosti.

Dodaj:

```yaml
risk_level: low | medium | high
```

Primeri:

* `low`: stabilna tehnična definicija;
* `medium`: tržna ocena ali adoption trend;
* `high`: investicijsko, regulatorno ali strateško priporočilo.

Višji risk pomeni:

* več zahtevanih neodvisnih virov;
* krajši review interval;
* strožji human gate;
* vidnejšo negotovost v objavi.

# 8. Minimalna implementacija za V1

Lean V1 ne potrebuje kompleksnega workflow engine-a.

Zadoščajo datoteke:

```text
/data/sources/*.yaml
/data/evidence/*.yaml
/data/claims/*.yaml
/data/ambiguities/*.yaml
/data/reviews/*.yaml
/data/events/*.yaml
/data/policies/*.yaml
```

In nekaj determinističnih validacij:

```text
- active claim mora imeti odobren review
- recommendation mora imeti assumptions
- contested claim ne sme biti objavljen kot nesporno dejstvo
- expired claim sproži review queue
- retired claim ne sme napajati nove vsebine
- vsak public claim mora imeti vsaj eno evidence povezavo
```

To lahko sprva deluje kot CLI/build-time pipeline brez baze.

# 9. Posodobljena celotna arhitektura

```text
Topic Brief
    ↓
Research Corpus
    ↓
Source Registry
    ↓
Evidence Objects
    ↓
Claim / Ambiguity Construction
    ↓
Human Review Gates
    ↓
Approved Knowledge Registry
    ↓
Publishing Views
    ↓
Markdown + MDX + JSON-LD + Astro

Horizontal control plane:

Evidence Lifecycle & Governance
├── status transitions
├── review policies
├── freshness monitoring
├── contradiction handling
├── dependency tracking
├── change impact analysis
├── version history
└── publication propagation
```

## Ključna arhitekturna posledica

Governance sloj ne določa, kaj je res. Določa:

* kakšna interpretacija je bila narejena;
* na podlagi česa;
* kdo jo je pregledal;
* pod katerimi pogoji velja;
* kdaj jo je treba ponovno preveriti;
* katere vsebine jo uporabljajo;
* kaj se zgodi, ko se spremeni.

To je tisto, kar FactForge spremeni iz generatorja člankov v **auditabilen sistem za upravljanje dokazno podprtega znanja**.
