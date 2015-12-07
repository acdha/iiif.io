---
title: "IIIF Editorial Process"
layout: spec
tags: [annex, presentation-api, image-api]
cssversion: 2
---

## Status of this Document
{:.no_toc}

This document is not subject to [IIIF's versioning semantics][iiif-semver]. Changes will be tracked within the document and its [internal change log][change-log]

**Authors:**

  * Michael Appleby, _Yale University_
  * Tom Crane, _Digirati_
  * Robert Sanderson, _Stanford University_
  * Jon Stroop, _Princeton University_
  * Simeon Warner, _Cornell University_
  {: .names}

{% include copyright.md %}

----

## Contents
{:.no_toc}
* Table of Discontent (will be replaced by macro)
{:toc}

## 1. Overview

The IIIF editors are responsible for facilitating discussions across the IIIF community, digesting those discussions into use cases, and reflecting those use cases into new and revised specifications for the community to implement. This process is intended to be as transparent as possible. This document exists to further that intention by defining the IIIF editorial process and the responsibilities and expectations of the individual editors.

## 2. Community Process

### 2.1 Proposals and Feedback

Community members should propose and discuss features and changes via [IIIF-Discuss][iiif-discuss]. However, there are a few other ways in which the IIIF Community can reach out to the editors. In particular, the IIIF holds a bi-weekly community conference call, the details and agenda for which are announced on IIIF-Discuss. Additionally, the [iiif.io issues on Github][iiif-github-issues] are open, and are especially useful for implementers who want to track the editorial discussion of a specific issue. Finally, conversations with individual editors are also possible, but are the least practical way to propose changes because the conversation will then have to be repeated to allow community input through one or more of the channels listed above.

### 2.2 Use Cases and Support

New specifications and changes to existing specification must have one or more [documented use cases][use-cases], supported by at least two institutions. In the case of breaking changes, where applicable, the documented use case must clearly demonstrate why the previous approach was flawed or insufficient.

@jpstroop: "...supported by at least two institutions". Do the institutions need to have other IIIF based technology or services in production? Otherwise is the following para enough to guard us against adding changes that never see implementation?
{: .warning}

@zimeon: Above suggests a greater role for more formally including [documented use cases][use-cases] repo.
{: .warning}

> @jpstroop: What's the advantage of having a use case / stories repo over just having a 'stories' label in our existing repo?
{: .warning}

### 2.3 Evaluation and Testing

In order to be considered ready for review, new features must have two open-source server-side implementations, at least one of which should be in production. New features must also have at least one open-source client-side implementation, which may be a proof-of-concept.

@jpstroop Regarding new features critera above: should we require that the source code be available, at least for proof-of-concept impls?.
{: .warning}

> @zimeon: I think we should require open-source in order to count, we can leave license unspecified.
{: .warning}

> @jpstroop: +1
{: .warning}

### 2.4 Community Review

New versions of specifications at or above 1.0 must be reviewed at an open meeting, to which the community is invited. These meetings will be announced on [IIIF-Discuss][iiif-discuss], [IIIF-Announce][iiif-announce] and other relevant community email lists. Such meetings must occur at least once per year, and should occur twice. The specifications will be frozen two weeks prior to a review meeting, and this review period will be announced to the same lists as above.

Proposed revisions to specifications must reference a change log as a means to help the community review the changes. This change log should differentiate between backwards compatible changes and breaking changes, and provide a brief summary of each change. See the [Image API 2.0 Change Log][image-20-changelog] for an example.

Objections should be registered in advance of the review meeting. Attendance at the review meeting is not required, but it should be noted that the review meeting is intended to be a platform for discussing any final concerns. Therefore, lack of attendance is likely to reduce the chances of an objection resulting in changes to a specification which has already been subject to the authorship, editorial, and reference implementation processes described above.

The editors shall ensure that there is a response to, and, where possible, resolution of any objections raised. The editors are responsible for considering the severity and importance of any remaining objections, and, ultimately, whether to seek additional community input and continue revision, or to proceed with publication of the new version of a specification.

@jpstroop: Should we compile a non-normative list of listservs?
{: .warning}

### 2.5 Frequency of Releases

No specification is perfect. New use cases surface, and refinements and clarifications need to be made. As such, specifications are generally considered to be under continuous revision. The editors will decide when new releases are proposed for review based on input from the community and balanced against the need for a degree of stability and relative to other IIIF priorities.

Starting with version 1.0 of new specifications (and after versions 2.0.0 of the Image and Presentation API specifications) the IIIF specifications follow semantic versioning as defined in the [IIIF Versioning Note][iiif-semver]. It is intended that minor, backwards compatible, releases will not be published more than once per year, and major releases will not be published more than once in two years.

Specification versions prior to 1.0 should be considered experimental, are not subject to community review, and may be updated with breaking changes at the editors' discretion.

## 3. Editors' Process

### 3.1 Terminology

The key words _MUST_, _MUST NOT_, _REQUIRED_, _SHALL_, _SHALL NOT_, _SHOULD_, _SHOULD NOT_, _RECOMMENDED_, and _OPTIONAL_ in this document are to be interpreted as described in [RFC 2119][rfc-2119].

### 3.2 Process for Suggesting Changes

Editorial collaboration takes place primarily in the [iiif.io repository on GitHub][iiif-github]. When editors submit changes for revision, they _MUST_ adhere to the following criteria:

 * There _SHOULD_ be a Github issue that explains the reason for the change and serves as a platform for discussion. Discussion regarding smaller changes may take place directly on a pull request.
 * The changes _MUST_ be made in a branch.
 * The branch _MUST_ pass all integration tests before making a pull request.
 * A link to the branch (i.e. _http://mybranch.iiif.io_) _MUST_ be included in the pull request relevant to the change.
 * Changes on the branch _SHOULD_ be squashed into one commit, with a reasonable commit message, and one parent commit that is the latest revision. Multiple commits are allowed when they are logical, but this should generally be avoided as it usually indicates that there are too many changes happening on one branch.

__N.B.:__ The current editors will help new editors with this process as necessary. Prior experience with Git or Github _MUST NOT_ be considered prerequisite knowledge when considering new editors.

### 3.3 Acceptance Criteria for Merging Changes

In addition to adhering to the guidelines above, there _MUST_ be agreement about the change among the editors. _Agreement_ is defined as follows:

 * There _MUST NOT_ be any "-1"s (or similar Emoji) in the latest comment from any editor before a merge.
 * __A majority__ of the editors, including the issuer of the pull request, _MUST_ actively agree ("+1") on any __non-normative__ change to a specification.
 * __All but one__ of the editors _MUST_ actively agree on any __normative__ change to a specification.
 * Even for non-specification content, __at least one__ editor, in addition to the issuer of the pull request, if applicable, must actively agree to any change on the [iiif.io][iiif-io] website.

@jpstroop: What about +0 as a way to say you're not bothered, i.e. you can't empathize with the use case, but don't see a problem with the change?
{: .warning}
> @zimeon: I'm not sure +0 serves our purpose, I don't think we are a large enough group that "sitting out" should be allowed
{: .warning}
> @jpstroop: :ok: with me, I just don't want to find us blocked on something obvious.
{: .warning}

In the event that an editor disagrees with a merge that has already happened, they should create a new issue that references the change in question, and explains the objection. This issue then serves as the discussion point for the objection which is subject to this same process. Reverts _SHOULD_ stay in the repository history, i.e., the process of reverting involve updating the HEAD version to reflect older content, and not erasing or re-writing history.

### 3.4 Face to Face Meetings

Editors will meet at least four times per year, and all editors _MUST_ attend at least three of those meetings per calendar year. Every effort will be made to co-locate at least one of the meetings with another meeting at which most of editors are already likely to be present.

The editors _MUST_ provide a summary of all meetings, and _SHOULD_ provide a summary of other interactions (e.g. closed conference calls leading up to a specification review period) at which changes and new specifications are discussed.

## 4. Editorial Team Membership and Selection

Per the IIIF Memorandum of Understanding covering the establishment of an IIIF Consortium, the editors may nominate additional editors to the IIIF-C at any time. All current editors _MUST_ agree before an invitation is issued. Editors will chose from strong participants within the community and/or experts willing to lend their knowledge and experience to new specifications. Opportunities to better the gender, race, and age balance of the existing editorial team will also be a consideration. New editors _MUST_ be approved by the IIIF Executive Group.

There is no set number of editors, but this does not mean that the number of existing editors will not be taken into account when considering new editors. The existing editors will seek out new or additional editors when they are lacking knowledge or significant empathy for use cases in an area that the community has agreed is important.

Editors _MUST_ agree to all of the processes set out in this document, including attendance at meetings, and to the [intellectual property conditions under which the specifications are published][spec-disclaimer]. They are responsible for confirming that these conditions are also acceptable to their employer, where applicable.

It is not expected that every editor comment on every issue, though they _SHOULD_ make every effort to do so. See [Acceptance Criteria for Merging Changes][merging-changes].

Editors may be dismissed from work on a specification, or the editorial group altogether, when they fail to meet the expectations of their colleagues, as described here.

## 6. Change Log

 | Date       | Description                                        |
 | ---------- | -------------------------------------------------- |
 | 2015-12-02 | Initial pass with comments (@jpstroop)             |
 | 2015-12-05 | Round two after editors' call discussion (@zimeon) |
 | 2015-12-05 | Wordsmithing and minor clarifications (@jpstroop)  |

[change-log]: #change-log "Change Log"
[iiif-announce]: https://groups.google.com/forum/#!forum/iiif-announce "IIIF Email Announcement List"
[iiif-discuss]: https://groups.google.com/forum/#!forum/iiif-discuss "IIIF Email Discussion List"
[use-cases]: https://github.com/IIIF/iiif-stories/issues "IIIF user stories and use cases"
[iiif-github-issues]: https://github.com/IIIF/iiif.io/issues "iiif.io issues"
[iiif-github]: https://github.com/IIIF/iiif.io "iiif.io on Github"
[iiif-io]: http://iiif.io "iiif.io"
[iiif-semver]: /api/annex/notes/semver.html "Versioning of APIs"
[image-20-changelog]: http://iiif.io/api/image/2.0/change-log.html "Changes for IIIF Image API Version 2.0"
[merging-changes]: #acceptance-criteria-for-merging-changes "2.2 Acceptance Criteria for Merging Changes"
[rfc-2119]: https://www.ietf.org/rfc/rfc2119.txt "RFC 2119"
[spec-disclaimer]: http://iiif.io/api/annex/notes/disclaimer.html "Specification Disclaimer"
{% include acronyms.md %}