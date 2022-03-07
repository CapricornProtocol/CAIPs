---
caip: 1
title: CAIP Purpose and Guidelines
status: Active
type: Meta
author: RodneyWinston <RodneyWinston-1@protonmail.com>
created: 2021-10-27
updated: 2022-03-07
---

## What is an CAIP?

CAIP stands for Capricorn Improvement Proposal. An CAIP is a design document providing information to the Capricorn community, or describing a new feature for Capricorn or its processes or environment. The CAIP should provide a concise technical specification of the feature and a rationale for the feature. The CAIP author is responsible for building consensus within the community and documenting dissenting opinions.

## CAIP Rationale

We intend CAIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Capricorn. Because the CAIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Capricorn implementers, CAIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the CAIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

## CAIP Types

There are three types of CAIP:

- A **Standard Track CAIP** describes any change that affects most or all Capricorn implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Capricorn. Furthermore Standard CAIPs can be broken down into the following categories. Standards Track CAIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification].
    - **Core** - improvements requiring a consensus fork (e.g. [CAIP5], [CAIP101]), as well as changes that are not necessarily consensus critical but may be relevant to “core dev” discussions (for example, [CAIP90], and the miner/node strategy changes 2, 3, and 4 of [CAIP86]).
    - **Networking** - includes improvements around [devp2p] ([CAIP8]) and [Light Capricorn Subprotocol], as well as proposed improvements to network protocol specifications of [whisper] and [swarm].
    - **Interface** - includes improvements around client [API/RPC] specifications and standards, and also certain language-level standards like method names ([CAIP6]) and [contract ABIs]. The label “interface” aligns with the [interfaces repo] and discussion should primarily occur in that repository before an CAIP is submitted to the CAIPs repository.
    - **ERC** - application-level standards and conventions, including contract standards such as token standards ([ERC20]), name registries ([ERC26], [ERC137]), URI schemes ([ERC67]), library/package formats ([CAIP82]), and wallet formats ([CAIP75], [CAIP85]).
- An **Informational CAIP** describes an Capricorn design issue, or provides general guidelines or information to the Capricorn community, but does not propose a new feature. Informational CAIPs do not necessarily represent Capricorn community consensus or a recommendation, so users and implementers are free to ignore Informational CAIPs or follow their advice.
- A **Meta CAIP** describes a process surrounding Capricorn or proposes a change to (or an event in) a process. Process CAIPs are like Standards Track CAIPs but apply to areas other than the Capricorn protocol itself. They may propose an implementation, but not to Capricorn's codebase; they often require community consensus; unlike Informational CAIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Capricorn development. Any meta-CAIP is also considered a Process CAIP.

It is highly recommended that a single CAIP contain a single key proposal or new idea. The more focused the CAIP, the more successful it tends to be. A change to one client doesn't require an CAIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does.

An CAIP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

## CAIP Work Flow

Parties involved in the process are you, the champion or *CAIP author*, the *CAIP editors*, and the *Capricorn Core Developers*.

:warning: Before you begin, vet your idea, this will save you time. Ask the Capricorn community first if an idea is original to avoid wasting time on something that will be be rejected based on prior research (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Capricorn is used. Examples of appropriate public forums to gauge interest around your CAIP include [the Capricorn subreddit], [the Issues section of this repository], and [one of the Capricorn Gitter chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your CAIP.

Your role as the champion is to write the CAIP using the style and format described below, shepherd the discussions in the appropriate forums, and build community consensus around the idea. Following is the process that a successful CAIP will move along:

```
[ WIP ] -> [ DRAFT ] -> [ LAST CALL ] -> [ ACCEPTED ] -> [ FINAL ]
```

Each status change is requested by the CAIP author and reviewed by the CAIP editors. Use a pull request to update the status. Please include a link to where people should continue discussing your CAIP. The CAIP editors will process these requests as per the conditions below.

* **Active** -- Some Informational and Process CAIPs may also have a status of “Active” if they are never meant to be completed. E.g. CAIP 1 (this CAIP).
* **Work in progress (WIP)** -- Once the champion has asked the Capricorn community whether an idea has any chance of support, they will write a draft CAIP as a [pull request]. Consider including an implementation if this will aid people in studying the CAIP.
    * :arrow_right: Draft -- If agreeable, CAIP editor will assign the CAIP a number (generally the issue or PR number related to the CAIP) and merge your pull request. The CAIP editor will not unreasonably deny an CAIP.
    * :x: Draft -- Reasons for denying draft status include being too unfocused, too broad, duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Capricorn philosophy.
* **Draft** -- Once the first draft has been merged, you may submit follow-up pull requests with further changes to your draft until such point as you believe the CAIP to be mature and ready to proceed to the next status. An CAIP in draft status must be implemented to be considered for promotion to the next status (ignore this requirement for core CAIPs).
    * :arrow_right: Last Call -- If agreeable, the CAIP editor will assign Last Call status and set a review end date (`review-period-end`), normally 14 days later.
    * :x: Last Call -- A request for Last Call status will be denied if material changes are still expected to be made to the draft. We hope that CAIPs only enter Last Call once, so as to avoid unnecessary noise on the RSS feed.
* **Last Call** 
    * :x: -- A Last Call which results in material changes or substantial unaddressed technical complaints will cause the CAIP to revert to Draft.
    * :arrow_right: Accepted (Core CAIPs only) -- A successful Last Call without material changes or unaddressed technical complaints will become Accepted.
    * :arrow_right: Final (Not core CAIPs) -- A successful Last Call without material changes or unaddressed technical complaints will become Final.
* **Accepted (Core CAIPs only)** -- This CAIP is in the hands of the Capricorn client developers.  Their process for deciding whether to encode it into their clients as part of a hard fork is not part of the CAIP process.
    * :arrow_right: Final -- Standards Track Core CAIPs must be implemented in at least three viable Capricorn clients before it can be considered Final. When the implementation is complete and adopted by the community, the status will be changed to “Final”.
* **Final** -- This CAIP represents the current state-of-the-art. A Final CAIP should only be updated to correct errata.

Other exceptional statuses include:

* **Deferred** -- This is for core CAIPs that have been put off for a future hard fork.
* **Rejected** -- An CAIP that is fundamentally broken or a Core CAIP that was rejected by the Core Devs and will not be implemented.
* **Active** -- This is similar to Final, but denotes an CAIP which may be updated without changing its CAIP number.
* **Superseded** -- An CAIP which was previously final but is no longer considered state-of-the-art. Another CAIP will be in Final status and reference the Superseded CAIP.

## What belongs in a successful CAIP?

Each CAIP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the CAIP, including the CAIP number, a short descriptive title (limited to a maximum of 44 characters), and the author details. 
- Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the CAIP.
- Abstract - a short (~200 word) description of the technical issue being addressed.
- Motivation (*optional) - The motivation is critical for CAIPs that want to change the Capricorn protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the CAIP solves. CAIP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Capricorn platforms (cpp-capricorn, go-capricorn, parity, capricornJ, capricornjs-lib, and others.
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All CAIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The CAIP must explain how the author proposes to deal with these incompatibilities. CAIP submissions without a sufficient backwards compatibility treatise may be rejected outright.
- Test Cases - Test cases for an implementation are mandatory for CAIPs that are affecting consensus changes. Other CAIPs can choose to include links to test cases if applicable.
- Implementations - The implementations must be completed before any CAIP is given status “Final”, but it need not be completed before the CAIP is merged as draft. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.
- Copyright Waiver - All CAIPs must be in the public domain. See the bottom of this CAIP for an example copyright waiver.

## CAIP Formats and Templates

CAIPs should be written in [markdown] format.
Image files should be included in a subdirectory of the `assets` folder for that CAIP as follow: `assets/caip-X` (for caip **X**). When linking to an image in the CAIP, use relative links such as `../assets/caip-X/image.png`.

## CAIP Header Preamble

Each CAIP must begin with an RFC 822 style header preamble, preceded and followed by three hyphens (`---`). The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` caip:` <CAIP number> (this is determined by the CAIP editor)

` title:` <CAIP title>

` author:` <a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s). Details are below.>

` * discussions-to:` \<a url pointing to the official discussion thread\>

` status:` <Draft | Last Call | Accepted | Final | Active | Deferred | Rejected | Superseded>

`* review-period-end:` <date review period ends>

` type:` <Standards Track (Core, Networking, Interface, ERC)  | Informational | Meta>

` * category:` <Core | Networking | Interface | ERC>

` created:` <date created on>

` * updated:` <comma separated list of dates>

` * requires:` <CAIP number(s)>

` * replaces:` <CAIP number(s)>

` * superseded-by:` <CAIP number(s)>

` * resolution:` \<a url pointing to the resolution of this CAIP\>

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The `author` header optionally lists the names, email addresses or usernames of the authors/owners of the CAIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the author header value must be:

> Random J. User &lt;address@dom.ain&gt;

or

> Random J. User (@username)

if the email address or GitHub username is included, and

> Random J. User

if the email address is not given.

#### `resolution` header

The `resolution` header is required for Standards Track CAIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the CAIP is made.

#### `discussions-to` header

While an CAIP is a draft, a `discussions-to` header will indicate the mailing list or URL where the CAIP is being discussed. As mentioned above, examples for places to discuss your CAIP include.

No `discussions-to` header is necessary if the CAIP is being discussed privately with the author.

As a single exception, `discussions-to` cannot point to GitHub pull requests.

#### `type` header

The `type` header specifies the type of CAIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or ERC).

#### `category` header

The `category` header specifies the CAIP's category. This is required for standards-track CAIPs only.

#### `created` header

The `created` header records the date that the CAIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

#### `updated` header

The `updated` header records the date(s) when the CAIP was updated with "substantional" changes. This header is only valid for CAIPs of Draft and Active status.

#### `requires` header

CAIPs may have a `requires` header, indicating the CAIP numbers that this CAIP depends on.

#### `superseded-by` and `replaces` headers

CAIPs may also have a `superseded-by` header indicating that an CAIP has been rendered obsolete by a later document; the value is the number of the CAIP that replaces the current document. The newer CAIP must have a `replaces` header containing the number of the CAIP that it rendered obsolete.

## Transferring CAIP Ownership

It occasionally becomes necessary to transfer ownership of CAIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred CAIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the CAIP process, or has fallen off the face of the 'net (i.e. is unreachable or isn't responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the CAIP. We try to build consensus around an CAIP, but if that's not possible, you can always submit a competing CAIP.

If you are interested in assuming ownership of an CAIP, send a message asking to take over, addressed to both the original author and the CAIP editor. If the original author doesn't respond to email in a timely manner, the CAIP editor will make a unilateral decision (it's not like such decisions can't be reversed :)).

## CAIP Editor Responsibilities

For each new CAIP that comes in, an editor does the following:

- Read the CAIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the CAIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the CAIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the CAIP is ready for the repository, the CAIP editor will:

- Assign an CAIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this CAIP)

- Merge the corresponding pull request

- Send a message back to the CAIP author with the next step.

Many CAIPs are written and maintained by developers with write access to the Capricorn codebase. The CAIP editors monitor CAIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on CAIPs. We merely do the administrative & editorial part.


