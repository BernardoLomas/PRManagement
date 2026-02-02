## 07 - Domain Model - Pigeon Racing Management System (PRMS)

1. Key domain entities
. Breeder 
. Dovecote
. Pigeon
. Lineage
. Health Record
. Breeding Event

2. Description of each entity 
> 2.1 Breeder 
> What it represents:
A person responsible for managing pigeons and making breeding decisions.

> Key responsibilities:
. Owns one or more dovecotes
. Registers and maintains pigeon data
. Makes breeding decisions

> Important notes:
. In the MVP, one breeder = one account
. Multi-breeder collaboration is out of scope

> 2.2 Dovecote
> What it represents:
A physical location where pigeons are housed and managed.

> Why it exists:
. Groups pigeons logically
. Represents the breeder’s operation

> Important notes:
. A breeder has one dovecote in the MVP
. Multiple dovecotes per breeder may exist in the future

> 2.3 Pigeon
> What it represents:
. An individual racing pigeon.

> Core identity:
. Ring identification
. Sex
. Birth year (or ring year)

> Why it matters:
. The pigeon is the center of the system.
. Everything else relates to it.

> 2.4 Lineage
> What it represents:
. The parent–child relationship between pigeons.

> Why it matters:
. Supports breeding decisions
. Preserves genetic history

> Important notes:
. A pigeon may have zero, one, or two registered parents
. Lineage data may be incomplete for older pigeons

> 2.5 Health Record
> What it represents:
. A historical note about a pigeon’s health condition or treatment.

> Purpose:
. Track diseases
. Track treatments
. Provide health history context

> Important notes:
. Health records are simple notes in the MVP
. No medical automation or diagnosis

> 2.6 Breeding Event
> What it represents:
. A breeding attempt between two pigeons.

> Purpose:
. Record which pigeons were paired
. Track offspring relationships

> Important notes:
. A breeding event may or may not produce offspring
. Results may be registered later

3. Relationships between entities 
. A Breeder owns one Dovecote
. A Dovecote contains many Pigeons
. A Pigeon belongs to one Dovecote
. A Pigeon may have parent Pigeons
. A Pigeon may have many Health Records
. A Breeding Event connects two Pigeons
. A Breeding Event may result in one or more Pigeons

4. Important business rules
. A pigeon must belong to a dovecote
. A pigeon must have a unique ring identifier within a dovecote
. A pigeon cannot be its own parent
. A breeding event must involve two pigeons of opposite sex
. Lineage information may be incomplete
. Health records cannot exist without a pigeon

5. What Is Explicitly Out of Scope 
> These concepts do not exist in the MVP domain:
. Competitions
. Financial transactions
. Marketplace / negotiation
. Social relationships between breeders
. AI recommendations

6. Open Questions & Uncertainties
These are expected at this stage.
. Can a pigeon belong to multiple dovecotes over time?
. How should deceased pigeons be handled?
. Is partial lineage acceptable?
. Should health records be mandatory or optional?
. Should breeding events be editable after creation?
