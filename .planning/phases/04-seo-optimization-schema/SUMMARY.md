# Plan 04-01: Schema Markup & Title Tag Fixes

## Status: Complete

## What Was Done

- Replaced homepage `LocalBusiness` schema with `ConcreteContractor` schema including full NAP (name, address with street/city/state/zip, phone, email), areaServed, openingHours, priceRange, and sameAs
- Fixed duplicate title tag on `concrete-restoration.html` — added "Services" to differentiate from homepage
- Added `Service` schema to all 6 service pages with name (matching H1 exactly), description (matching meta description), provider (ConcreteContractor reference), areaServed (3 counties), and serviceType

## Commits

1. `4f6d9a0` — fix: upgrade homepage schema from LocalBusiness to ConcreteContractor with full NAP
2. `fbc986d` — fix: differentiate concrete-restoration.html title tag from homepage
3. `f893cfd` — feat: add Service schema to concrete-restoration.html
4. `011601d` — feat: add Service schema to waterproofing.html
5. `f1d7c66` — feat: add Service schema to stucco-repair.html
6. `6439eed` — feat: add Service schema to protective-coatings.html
7. `f349ce5` — feat: add Service schema to balcony-restoration.html
8. `efa6945` — feat: add Service schema to painting.html

## Verification

- All 7 pages have valid JSON-LD schema blocks (1 per page)
- Homepage schema `@type` is `ConcreteContractor`
- All service page schemas have `@type: Service`
- Each service page schema `name` matches its `<h1>` tag exactly
- concrete-restoration.html title differs from index.html title
- All schema JSON validated as syntactically correct

## Adjustment from Plan

Schema `name` values were adjusted to match actual `<h1>` tags rather than the plan's guesses. The plan assumed "Waterproofing Services in South Florida" etc., but the actual H1s are shorter (e.g., "Waterproofing South Florida"). This is correct — schema `name` must match visible content.
