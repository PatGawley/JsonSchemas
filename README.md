# JsonSchemas

This repo contains Json schemas used by the Nomination Process which handles the processing bonus card nominations.

The nomination process is triggered by the NomincatedCardLeases on the NominatedCard collection in the BonusCard CosmosDb. All updates are archived in the Bonus Card journal (new requirement not specifically asked for but I believe it will be useful) but only updates with an onboarding status of REQUESTED are sent down the nomination process. The following are possible scenarios: -

- **Digital request on registration** - New customer (for the channel e.g. Online) requesting a digital card
- **New Card nomination on registration** - New customer(for the channel e.g. Online) nominating a new physical card (not registered in loyalty)
- **Card nomination on registration** - New customer(for the channel e.g. Online) nominating a physical card (already registered in loyalty)
- **Digital request** - Existing customer nominating a digital card for the first time
- **Digital nomination** - Existing customer nominating a digital card where they have previously successfully nominated a digital card and had one dispensed
- **New Card nomination** - Existing customer nominating a new physical card (not registered in loyalty)
- **Card nomination** - Existing customer nominating a physical card (previously registered in loyalty)

The happy path for each scenario is a document in the NominatedCard collection with a status of ONBOARDED.
