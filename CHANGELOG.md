# Change Log
All notable changes to this project will be documented in this file.

The format is based on the [KeepAChangeLog] project.

[KeepAChangeLog]: https://keepachangelog.com/

## Unreleased
### Changed
- [#847] Using pydantic for settings instead of custom class

[#847]: https://github.com/CZ-NIC/pyoidc/pull/847

## 1.5.0 [2022-12-14]

### Changed
- [#827] Added support for python 3.11
- [#830], [#831] Allow null and empty values in UserInfo responses, but filter them out. 
- [#832] Added support for mypy with --no_implicit_optional=True

### Fixed
- [#826], [#829] Fixed RP-Initiated Logout To Accept id_token_hint

## Removed

- [#820] Removed Client.grant_from_state method.

[#820]: https://github.com/CZ-NIC/pyoidc/pull/820
[#826]: https://github.com/CZ-NIC/pyoidc/issues/826
[#827]: https://github.com/CZ-NIC/pyoidc/issues/827
[#829]: https://github.com/CZ-NIC/pyoidc/pull/829
[#830]: https://github.com/CZ-NIC/pyoidc/issues/830
[#831]: https://github.com/CZ-NIC/pyoidc/pull/831
[#832]: https://github.com/CZ-NIC/pyoidc/pull/832

## 1.4.0 [2022-05-23]

### Changed
- [#810] Drop python 3.6 support

### Fixed
- [#812] Fixed parsing of zero content lenght responses

[#810]: https://github.com/CZ-NIC/pyoidc/pull/810
[#812]: https://github.com/CZ-NIC/pyoidc/pull/812

## 1.3.0 [2021-07-09]

### Changed
- [#763] Drop python 3.5 support

### Added
- [#790] Support for dict in Client.parse_response formats
- [#739] Better error message for providers which return HTTP Error 405 on userinfo
- [#723] Add settings class to handle settings related to Client and Server

[#723]: https://github.com/CZ-NIC/pyoidc/pull/723/
[#739]: https://github.com/CZ-NIC/pyoidc/pull/739/
[#763]: https://github.com/CZ-NIC/pyoidc/pull/763/
[#790]: https://github.com/CZ-NIC/pyoidc/pull/790

## 1.2.1 [2020-12-01]

### Fixed
- Fixed several client vulnerabilities (CVE-2020-26244)

## 1.2.0 [2020-02-05]

### Fixed
- [#727] OAuth client request using Client Credentials grant

### Added
- [#719] Add support for JWT registration tokens
- [#728] OAuth client request using Extension grant
- [#731] Session cookie need to be visible to OP IFrame.

[#719]: https://github.com/CZ-NIC/pyoidc/pull/719
[#727]: https://github.com/CZ-NIC/pyoidc/issues/727
[#728]: https://github.com/CZ-NIC/pyoidc/issues/728
[#731]: https://github.com/CZ-NIC/pyoidc/pull/731

## 1.1.2 [2019-11-23]

### Fixed
- [#711] Deal with no post_logout_redirect_uri
- [#712] Set Content-Type on BackChannel logout POST.
- [#717] Missing OP logout metadata.

[#711]: https://github.com/CZ-NIC/pyoidc/pull/711
[#712]: https://github.com/CZ-NIC/pyoidc/pull/712
[#717]: https://github.com/CZ-NIC/pyoidc/pull/717

## 1.1.1 [2019-11-04]

### Fixed
- [#708] Wants the original non-parsed JWT and not an IDToken instance.

[#708]: https://github.com/CZ-NIC/pyoidc/pull/708

## 1.1.0 [2019-10-25]

### Changed

- [#688] Second stage of adding logout support.
- [#700] Third stage of adding logout support, provider side

### Fixed
- [#602] Fixed uncaught error on unpacking of message
- [#679] Make `state` optional in `EndSessionRequest`
- [#683] Fix basic_auth with client password
- [#698] `state` in `EndSessionRequest` request args and kwargs different

### Removed
- [#671] Removed deprecated request/response_cls kwargs from Provider/Client methods
- [#677] Removed more deprecated code

[#671]: https://github.com/CZ-NIC/pyoidc/pull/671
[#677]: https://github.com/CZ-NIC/pyoidc/pull/677
[#602]: https://github.com/CZ-NIC/pyoidc/issues/602
[#679]: https://github.com/CZ-NIC/pyoidc/pull/679
[#683]: https://github.com/CZ-NIC/pyoidc/issues/683
[#688]: https://github.com/CZ-NIC/pyoidc/pull/688
[#698]: https://github.com/CZ-NIC/pyoidc/pull/698
[#700]: https://github.com/CZ-NIC/pyoidc/pull/700

## 1.0.1 [2019-06-30]

### Fixed
- [#669] Install as PEP561 compliant package

[#669]: https://github.com/CZ-NIC/pyoidc/issues/669

## 1.0.0 [2019-06-19]

### Fixed
- [#341] Using constant time comparison for password verification
- [#598] Move alabaster from runtime dependencies to docs
- [#398] Do not echo cookies that do not belong to us
- [#607] Fixed key recovery on encryption of payload
- [#618] Prettified `client_management.py` CLI and wrapped it as
         a setup.py console script `oic-client-management`
- [#615] Fix ROPC grant in the extensions provider
- [#640] Use more secure random generator for client_secret
- [#639] Make sure symmetric keys are available after server restart
- [#146] Make SessionDB storage conductive with multi-session

### Changed
- [#578] Dropped python 2.7 support
- [#612] Dropped python 3.4 support
- [#588] Switch to defusedxml for XML parsing
- [#605] Message.c_param dictionary values have to be a ParamDefinition namedtuple type
- [#56] Updated README, CLI help texts, pip requirements.txt and such for OP2,
        making it into a stand-alone example easy for beginners to take on 
- [#624] token_endpoint implementation and kwargs have been changed
- [#629] Duplicated methods in oic.oic classes were removed.
- [#642] Deprecated `bearer_auth` method.
- [#631] Refactored message type handling in Client/Provider.
- [#644] refresh_db kwarg in SessionDB has been deprecated

### Added
- [#655] Host can be forced on webfinger discovery
- [#441] CookieDealer now accepts secure and httponly params
- [#638] Moved `providerinfo_endpoint` from `oic.extensions` to `oic.oauth2`
- [#664] Messages needed for Single-Sign-Out Support

[#655]: https://github.com/CZ-NIC/pyoidc/issues/655
[#598]: https://github.com/CZ-NIC/pyoidc/issues/598
[#588]: https://github.com/CZ-NIC/pyoidc/issues/588
[#341]: https://github.com/CZ-NIC/pyoidc/issues/341
[#398]: https://github.com/CZ-NIC/pyoidc/issues/398
[#605]: https://github.com/CZ-NIC/pyoidc/pull/605
[#607]: https://github.com/CZ-NIC/pyoidc/issues/607
[#441]: https://github.com/CZ-NIC/pyoidc/issues/441
[#612]: https://github.com/CZ-NIC/pyoidc/pull/612
[#618]: https://github.com/CZ-NIC/pyoidc/pull/618
[#56]: https://github.com/CZ-NIC/pyoidc/issues/56
[#624]: https://github.com/CZ-NIC/pyoidc/pull/624
[#629]: https://github.com/CZ-NIC/pyoidc/issues/629
[#615]: https://github.com/CZ-NIC/pyoidc/issues/615
[#640]: https://github.com/CZ-NIC/pyoidc/issues/640
[#642]: https://github.com/CZ-NIC/pyoidc/pull/642
[#639]: https://github.com/CZ-NIC/pyoidc/issues/639
[#631]: https://github.com/CZ-NIC/pyoidc/issues/631
[#638]: https://github.com/CZ-NIC/pyoidc/issues/638
[#146]: https://github.com/CZ-NIC/pyoidc/issues/146
[#664]: https://github.com/CZ-NIC/pyoidc/pull/664
[#644]: https://github.com/CZ-NIC/pyoidc/issues/644

## 0.15.1 [2019-01-31]

### Fixed
- [#592] Do not append cookie header if there is nothing to append
- [#591] Fix verification of encrypted id_token
- [#601] Fix headers od encrypted id_token

[#578]: https://github.com/CZ-NIC/pyoidc/issues/578
[#592]: https://github.com/CZ-NIC/pyoidc/issues/592
[#591]: https://github.com/CZ-NIC/pyoidc/issues/591
[#601]: https://github.com/CZ-NIC/pyoidc/pull/600

## 0.15.0 [2019-01-17]

### Fixed
- [#553] Made sure a reload would not lead to duplicated keys in a keybundle.
- [#557] Fixed PKCE verification
- [#562] Fixed error response from oic request with invalid params
- [#565] Fixed checking token_type in AuthorizationResponse
- [#547] Fixed get_userinfo_claims method
- [#268] Fixed SessionDB.revoke_token implementation
- [#571] Return error when when resolving request_uri fails
- [#579] Fix error with unicode chars in redirect_uris
- [#581] Fix error in verification of sector_identifier
- [#542] Updated examples
- [#587] Fix JWKS content type detection
- [#582] Handling import of non-compliant JWKS

### Added
- [#577] Check that issuer of a signed JWT exists in the KeyJar used to verify the signature.
- [#566] Added timeout to communications to remote servers
- [#590] Worked on support for RP initiated logout

[#553]: https://github.com/CZ-NIC/pyoidc/pull/553
[#557]: https://github.com/CZ-NIC/pyoidc/pull/557
[#562]: https://github.com/CZ-NIC/pyoidc/issues/562
[#565]: https://github.com/CZ-NIC/pyoidc/pull/565
[#577]: https://github.com/CZ-NIC/pyoidc/pull/577
[#566]: https://github.com/CZ-NIC/pyoidc/issues/566
[#547]: https://github.com/CZ-NIC/pyoidc/issues/547
[#268]: https://github.com/CZ-NIC/pyoidc/issues/268
[#571]: https://github.com/CZ-NIC/pyoidc/pull/571
[#579]: https://github.com/CZ-NIC/pyoidc/issues/579
[#581]: https://github.com/CZ-NIC/pyoidc/issues/581
[#542]: https://github.com/CZ-NIC/pyoidc/pull/542
[#587]: https://github.com/CZ-NIC/pyoidc/pull/587
[#582]: https://github.com/CZ-NIC/pyoidc/pull/582
[#590]: https://github.com/CZ-NIC/pyoidc/pull/590

## 0.14.0 [2018-05-15]

### Fixed
- [#534] Fixed a bug in client_secret_basic authentication
- [#503] Fix error on UserInfo endpoint for removed clients
- [#508] JWT now uses verify keys for JWT verification
- [#502] IntrospectionEndpoint now returns False if it encounters any error as per specs
- [#481] Loading AuthnEvent from session
- [#492] Do not verify JWT signature on distributed claims
- [#526] Cleaned up extra claims from UserInfo with distributed claims
- [#528] Fix faulty redirect_uri with query
- [#532] Fix userinfo endpoint without auhtn_event in session
- [#528] Fix faulty redirect_uri with query
- [#498] Clean up replaced tokens on refresh and add Client.clean_tokens to clean old and replaced tokens

### Removed
- [#494] Methods and functions deprecated in previous releases have been removed

### Changed
- [#507] Altered structure of client_db. It no longer stores mapping of ``registration_access_token`` to ``client_id``
- [#481] AuthnEvent in session is now represented as JSON

### Added
- [#496] Ability to specify additional supported scopes for oic.Provider
- [#432] Ability to specify Initial Access Token for ``Client.register``

[#494]: https://github.com/CZ-NIC/pyoidc/issues/494
[#496]: https://github.com/CZ-NIC/pyoidc/issues/496
[#503]: https://github.com/CZ-NIC/pyoidc/issues/503
[#508]: https://github.com/CZ-NIC/pyoidc/issues/508
[#507]: https://github.com/CZ-NIC/pyoidc/issues/507
[#502]: https://github.com/CZ-NIC/pyoidc/issues/502
[#481]: https://github.com/CZ-NIC/pyoidc/issues/481
[#492]: https://github.com/CZ-NIC/pyoidc/issues/492
[#432]: https://github.com/CZ-NIC/pyoidc/issues/432
[#526]: https://github.com/CZ-NIC/pyoidc/issues/526
[#528]: https://github.com/CZ-NIC/pyoidc/issues/528
[#532]: https://github.com/CZ-NIC/pyoidc/pull/532
[#498]: https://github.com/CZ-NIC/pyoidc/issues/498
[#534]: https://github.com/CZ-NIC/pyoidc/pull/534

## 0.13.1 [2018-04-06]

### Fixed
- [#515]: Fix arguments to WSGI start_response

[#515]: https://github.com/CZ-NIC/pyoidc/issues/515

## 0.13.0 [2018-02-19]

### Added
- [#493] grant_types specification should follow the response_types specification in a client registration request.
- [#469] Allow endpoints to have query parts
- [#443] Ability to specify additional supported claims for oic.Provider
- [#134] Added method kwarg to registration_endpoint that enables the client to read/modify registration
- [#478] Addedd base-class for Client databases ``oic.utils.clientdb.BaseClientDatabase``
- [#334] Ability to specify custom template rendering function for form_post and verify_logout

### Changed
- [#134] ``l_registration_enpoint`` has been deprecated, use ``create_registration`` instead
- [#457] pyldap is now an optional dependency. ``oic.utils.authn.ldapc`` and ``oic.utils.userinfo.ldap_info`` raise
         ``ImportError`` on import if ``pyldap`` is not present
- [#471] ``ca_certs`` option has been removed, use ``verify_ssl`` instead
- [#483] ``oic.oauth2.uril.verify_header`` now raises ``ValueError`` insteaad of ``AssertionError``.
- [#491] ``oic.utils.http_util.Response.status`` is deprecated in favor of ``status_code``
- [#491] Some functions and kwargs in ``oic.oauth2`` module are deprecated

### Removed
- [#334] Removed template_lookup and template kwargs from oic.Provider

### Fixed
- [#430] Audience of a client assertion is endpoint dependent.
- [#427] Made matching for response_types order independent for authorization requests
- [#399] Matching response_types for authz requests is too strict
- [#436] Fixed client.read_registration
- [#446] Fixed provider.read_registration
- [#449] Fixed creation of error_response on client registration
- [#445] Fixed get_client_id
- [#421] Fixed handling of unicode in sanitize function
- [#145] Successful token endpoint responses have correct no-cache headers
- [#352] Fixed broken windows test for ``test_provider_key_setup``. 
- [#475] ``get_verify_key`` returns inactive ``sig`` keys for verification
- [#429] An expired token is not possible to use.
- [#485] Skip import of improperly defined keys
- [#370] Use oic.oic.Provider.endp instead of dynamic provider.endpoints in examples

### Security
- [#486] SystemRandom is not imported correctly, so various secrets get initialized with bad randomness

[#493]: https://github.com/CZ-NIC/pyoidc/pull/493
[#430]: https://github.com/CZ-NIC/pyoidc/pull/430
[#427]: https://github.com/CZ-NIC/pyoidc/pull/427
[#399]: https://github.com/CZ-NIC/pyoidc/issues/399
[#436]: https://github.com/CZ-NIC/pyoidc/pull/436
[#443]: https://github.com/CZ-NIC/pyoidc/pull/443
[#446]: https://github.com/CZ-NIC/pyoidc/issues/446
[#449]: https://github.com/CZ-NIC/pyoidc/issues/449
[#445]: https://github.com/CZ-NIC/pyoidc/issues/445
[#421]: https://github.com/CZ-NIC/pyoidc/issues/421
[#134]: https://github.com/CZ-NIC/pyoidc/issues/134
[#457]: https://github.com/CZ-NIC/pyoidc/issues/457
[#145]: https://github.com/CZ-NIC/pyoidc/issues/145
[#471]: https://github.com/CZ-NIC/pyoidc/issues/471
[#352]: https://github.com/CZ-NIC/pyoidc/issues/352
[#475]: https://github.com/CZ-NIC/pyoidc/issues/475
[#478]: https://github.com/CZ-NIC/pyoidc/issues/478
[#483]: https://github.com/CZ-NIC/pyoidc/pull/483
[#429]: https://github.com/CZ-NIC/pyoidc/issues/424
[#485]: https://github.com/CZ-NIC/pyoidc/pull/485
[#486]: https://github.com/CZ-NIC/pyoidc/issues/486
[#370]: https://github.com/CZ-NIC/pyoidc/issues/370
[#491]: https://github.com/CZ-NIC/pyoidc/pull/491
[#334]: https://github.com/CZ-NIC/pyoidc/issues/334
[#469]: https://github.com/CZ-NIC/pyoidc/pull/469

## 0.12.0 [2017-09-25]

### Fixed
- [#419]: Inconsistent release numbers/tags
- [#420]: Distributed claims

[#419]: https://github.com/CZ-NIC/pyoidc/issues/419
[#420]: https://github.com/CZ-NIC/pyoidc/pull/420

## 0.11.1.0 [2017-08-26]

### Fixed
- [#405]: Fix generation of endpoint urls
- [#411]: Empty lists not indexable
- [#413]: Fix error when wrong response_mode requested
- [#418]: Made phone_number_claim be boolean and fixed a bug when importing JSON (non-boolean where boolean expected)

[#418]: https://github.com/CZ-NIC/pyoidc/pull/418
[#411]: https://github.com/CZ-NIC/pyoidc/issues/411
[#405]: https://github.com/CZ-NIC/pyoidc/issues/405
[#413]: https://github.com/CZ-NIC/pyoidc/issues/413

## 0.11.0.0 [2017-07-07]

### Changed
- [#318]: `oic.utils.authn.saml` raises `ImportError` on import if optional `saml2` dependency is not present.
- [#324]: Make the Provider `symkey` argument optional.
- [#325]: `oic.oic.claims_match` implementation refactored.
- [#368]: `oic.oauth2.Client.construct_AccessTokenRequest()` as well as `oic.oic.Client` are now able to perform proper Resource Owner Password Credentials Grant
- [#374]: Made the to_jwe/from_jwe methods of Message accept list of keys value of parameter keys.
- [#387]: Refactored the `oic.utils.sdb.SessionDB` constructor API.
- [#380]: Made cookie_path and cookie_domain configurable via Provider like the cookie_name.
- [#386]: An exception will now be thrown if a sub claim received from the userinfo endpoint is not the same as a sub claim previously received in an ID Token.
- [#392]: Made sid creation simpler and faster

### Fixed
- [#317]: Resolved an `AttibuteError` exception under Python 2.
- [#313]: Catch exception correctly
- [#319]: Fix sanitize on strings starting with "B" or "U"
- [#330]: Fix client_management user input being eval'd under Python 2
- [#358]: Fixed claims_match
- [#362]: Fix bad package settings URL
- [#369]: The AuthnEvent object is now serialized to JSON for the session.
- [#373]: Made the standard way the default when dealing with signed JWTs without 'kid'. Added the possibility to override this behavior if necessary.
- [#401]: Fixed message decoding and verifying errors.

### Security
- [#349]: Changed crypto algorithm used by `oic.utils.sdb.Crypt` for token encryption to Fernet. Old stored tokens are incompatible.
- [#363]: Fixed IV reuse for CookieDealer class. Replaced the encrypt-then-mac construction with a proper AEAD (AES-SIV).

[#401]: https://github.com/CZ-NIC/pyoidc/pull/401
[#386]: https://github.com/CZ-NIC/pyoidc/pull/386
[#380]: https://github.com/CZ-NIC/pyoidc/issues/380
[#317]: https://github.com/CZ-NIC/pyoidc/pull/317
[#313]: https://github.com/CZ-NIC/pyoidc/issues/313
[#387]: https://github.com/CZ-NIC/pyoidc/pull/387
[#318]: https://github.com/CZ-NIC/pyoidc/pull/318
[#319]: https://github.com/CZ-NIC/pyoidc/pull/319
[#324]: https://github.com/CZ-NIC/pyoidc/pull/324
[#325]: https://github.com/CZ-NIC/pyoidc/pull/325
[#330]: https://github.com/CZ-NIC/pyoidc/issues/330
[#349]: https://github.com/CZ-NIC/pyoidc/issues/349
[#358]: https://github.com/CZ-NIC/pyoidc/pull/358
[#362]: https://github.com/CZ-NIC/pyoidc/pull/362
[#363]: https://github.com/CZ-NIC/pyoidc/issues/363
[#368]: https://github.com/CZ-NIC/pyoidc/issues/368
[#369]: https://github.com/CZ-NIC/pyoidc/pull/369
[#373]: https://github.com/CZ-NIC/pyoidc/pull/373
[#374]: https://github.com/CZ-NIC/pyoidc/pull/374
[#392]: https://github.com/CZ-NIC/pyoidc/issues/392

## 0.10.0.0 [2017-03-28]

### Changed
- [#291]: Testing more relevant Python versions.
- [#296]: `parse_qs` import from `future.backports` to `future.moves`.
- [#188]: Added `future` dependency, updated dependecies
- [#305]: Some import were removed from `oic.oauth2` and `oic.oic.provider`, please import them from respective modules (`oic.oath2.message` and `oic.exception`).

### Removed
- [#294]: Generating code indices in documentation.

### Fixed
- [#295]: Access token issuance and typo/exception handling.

[#291]: https://github.com/CZ-NIC/pyoidc/pull/291
[#294]: https://github.com/CZ-NIC/pyoidc/pull/294
[#295]: https://github.com/CZ-NIC/pyoidc/pull/295
[#296]: https://github.com/CZ-NIC/pyoidc/pull/296
[#188]: https://github.com/CZ-NIC/pyoidc/issues/188
[#305]: https://github.com/CZ-NIC/pyoidc/pull/305

## 0.9.5.0 [2017-03-22]

### Added
- [#276]: Use a Change log for change history.
- [#277]: Use pip-tools for dependency management.

[#276]: https://github.com/CZ-NIC/pyoidc/pull/276
[#277]: https://github.com/CZ-NIC/pyoidc/pull/277

### Removed
- [#274]: Moved `oidc_fed` to [fedoidc].

[#274]: https://github.com/CZ-NIC/pyoidc/pull/274
[fedoidc]: https://github.com/CZ-NIC/fedoidc

### Changed
- [#273]: Allow webfinger accept `kwargs`.

[#273]: https://github.com/CZ-NIC/pyoidc/pull/273

### Fixed
- [#286]: Account for missing code in the SessionDB.

[#286]: https://github.com/CZ-NIC/pyoidc/pulls/286

## 0.9.4.0 [2016-12-22]
No change log folks. Sorry.
