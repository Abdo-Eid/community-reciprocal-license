# Choosing a license

Choose the license according to your project's priorities, not a universal preference.

| Goal | Consider |
| --- | --- |
| Maximize library/SDK integration or upstream adoption | MIT or Apache-2.0 |
| Protect a self-hosted platform from commercial resale while permitting private internal customization | CRL Distribution |
| Require operational improvements to be shared even when used internally | CRL Standard |
| Offer a paid hosted or proprietary edition alongside a free community edition | Either CRL variant, provided you hold commercial licensing rights |

## Practical examples

A voice AI debugger intended for adoption by existing upstream projects may benefit from keeping MIT. If a new debugger is independently owned and anti-resale protection matters, CRL-D can permit private acoustic-analysis views while still requiring disclosure of distributed modifications and restricting commercial hosted replay.

An LLM observability platform may use permissively licensed SDKs and CRL-D for its independently owned server, dashboard and evaluation engine. CRL-S is appropriate if reciprocal internal improvements are more important than minimizing enterprise legal friction.

## Adoption checklist

1. Obtain independent legal review of the exact license.
2. Audit dependencies, existing contributor rights and any prior license grants.
3. Select one variant explicitly and copy its complete text to your project's LICENSE file.
4. Fill the project-specific header with your own upstream repository and contacts.
5. Document component boundaries and contributor policy. A separate, affirmatively accepted CLA may support commercial relicensing.
6. Keep version history and do not represent either variant as OSI-approved open source.

Previously granted MIT permissions are not withdrawn by adopting CRL for future releases. Switching between CRL variants also requires authorization from relevant rights holders. These examples are hypothetical, not advice about a particular repository or pull request.
