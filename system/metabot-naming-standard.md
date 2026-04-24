# MetaBOT Naming Standard

## Scope

Scope defines ownership or adaptation level.

Allowed values:

- MCA → internal MetaCODE bots
- generic → reusable template bots
- <CLIENT_CODE> → client-specific bots

## CLIENT_CODE rules

- must be uppercase
- must be short
- must be deterministic
- must match project/client naming

Examples:

MCA
generic
TRIUMF
BZPM

## Scope rule

Every bot must explicitly define its scope.

Forbidden:

- missing scope
- ambiguous scope
- dynamic or random scope values
