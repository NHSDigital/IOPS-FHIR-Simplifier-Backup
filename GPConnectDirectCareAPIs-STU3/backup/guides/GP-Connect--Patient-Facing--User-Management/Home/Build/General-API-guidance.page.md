## {{page-title}}

## Purpose

This site is intended for use by software developers looking to build a conformant GP Connect API interface with a focus on general API implementation guidance.

### Notational conventions

The keywords ‘**MUST**’, ‘**MUST NOT**’, ‘**REQUIRED**’, ‘**SHALL**’, ‘**SHALL NOT**’, ‘**SHOULD**’, ‘**SHOULD NOT**’, ‘**RECOMMENDED**’, ‘**MAY**’, and ‘**OPTIONAL**’ on this site are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## General standards

Information on the technical standards that SHALL be conformed to can be found in the sections below and throughout the GP Connect specification.

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> Any additional principles highlighted in the GP Connect specification MUST take precedence over those defined in these technical standards.
</div>

## Internet standards

Clients and servers SHALL be conformant to the following Internet Engineering Task Force (IETF) request for comments (RFCs), which are the principal technical standards that underpin the design and development of the internet and thus FHIR's APIs.

- transport level integration SHALL be via HTTP as defined in the following RFCs: [RFC 7230](https://tools.ietf.org/html/rfc7230), [RFC 7231](https://tools.ietf.org/html/rfc7231), [RFC 7232](https://tools.ietf.org/html/rfc7232), [RFC 7233](https://tools.ietf.org/html/rfc7233), [RFC 7234](https://tools.ietf.org/html/rfc7234) and [RFC 7235](https://tools.ietf.org/html/rfc7235)
- transport level security SHALL be via TLS/HTTPS as defined in [RFC 5246](https://tools.ietf.org/html/rfc5246) and [RFC 6176](https://tools.ietf.org/html/rfc6176)
- HTTP Strict Transport Security (HSTS) as defined in [RFC 6797](https://tools.ietf.org/html/rfc6797) SHALL be employed to protect against protocol downgrade attacks and cookie hijacking

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> NHS Digital is currently evaluating how <a href="http://www.w3.org/TR/cors/">cross-origin resource sharing</a> (CORS) will be handled for web and mobile based applications.
</div>