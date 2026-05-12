---
###
# Internet-Draft Markdown Template
#
# Rename this file from draft-todo-yourname-protocol.md to get started.
# Draft name format is "draft-<yourname>-<workgroup>-<name>.md".
#
# For initial setup, you only need to edit the first block of fields.
# Only "title" needs to be changed; delete "abbrev" if your title is short.
# Any other content can be edited, but be careful not to introduce errors.
# Some fields will be set automatically during setup if they are unchanged.
#
# Don't include "-00" or "-latest" in the filename.
# Labels in the form draft-<yourname>-<workgroup>-<name>-latest are used by
# the tools to refer to the current version; see "docname" for example.
#
# This template uses kramdown-rfc: https://github.com/cabo/kramdown-rfc
# You can replace the entire file if you prefer a different format.
# Change the file extension to match the format (.xml for XML, etc...)
#
###
title: "AIPREF Vocabulary Parameters"
category: info

docname: draft-zehta-aipref-parameters-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Web and Internet Transport"
workgroup: "AI Preferences"
keyword:
 - AI Preferences
 - Artificial Intelligence
venue:
  group: "AI Preferences"
  type: "Working Group"
  mail: "ai-control@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/ai-control/"
  github: "TimidRobot/ietf-aipref-parameters"
  latest: "https://TimidRobot.github.io/ietf-aipref-parameters/draft-zehta-parameters.html"

author:
 -
    fullname: "Timid Robot Zehta"
    organization: "Creative Commons"
    email: "timid@creativecommons.org"

normative:
  FIELDS: RFC9651
  URI: RFC3986
  VOCAB:
    title: "A Vocabulary For Expressing AI Usage Preferences"
    date: draft-ietf-aipref-vocab-date
    seriesinfo:
      Internet-Draft: draft-ietf-aipref-vocab-06
    author:
      -
        fullname: Paul Keller
        organization: Open Future
      -
        fullname: Martin Thomson
        role: editor
        organization: Mozilla

informative:
  DISPLAY:
    title: "A Vocabulary for Controlling Usage of Content Collected by Search and AI Crawlers"
    date: 2026-03-25
    seriesinfo:
      Internet-Draft: draft-madhavan-aipref-displaybasedpref-02
    author:
      -
        fullname: Krishna Madhavan
        organization: Microsoft Corporation
      -
        fullname: Fabrice Canel
        organization: Microsoft Corporation
      -
        fullname: Jordan Gimbel
        organization: Microsoft Corporation
      -
        fullname: Sonia Cooper
        organization: Microsoft Corporation

...

--- abstract

This document defines how parameters can be added to AI Preferences.


--- middle

# Introduction

This document defines how parameters can be added to AI Preferences {{VOCAB}}.


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Parameters

As noted in {{Section 6 of VOCAB}}:

> The format relies on the Dictionary type defined in
> {{Section 3.2 of !FIELDS}}.

The AI Preferences can be extended with parameters. The parameter syntax is
defined in ({{Section 3.1.2 of !FIELDS}}):

> Parameters are an ordered map of key-value pairs that are associated with an
> Item (Section 3.3) [...]. The keys are unique within the scope of the
> Parameters they occur within, and the values are bare items (i.e., they
> themselves cannot be parameterized; see Section 3.3).


## URI-refernces

If the value of a parameter contains a URI-reference ({{Section 4.1 of
URI}}) and its value is not a valid URI-reference, the parameter MUST be
ignored. If its value is a relative reference ({{Section 4.2 of URI}}), it MUST
be resolved ({{Section 5 of URI}}) before being used.


## Examples

Generic example:

~~~
ai-train=n;foo=y
~~~

Assuming a content holder wants to highlight the presense of a tip jar:
~~~
ai-train=y;tipjar=/tipjar
~~~

Example of categories from {{DISPLAY}} converted to parameters:
~~~
ai-train=n,search=y;display-text=y;max-text-length=160
~~~


# Security Considerations

See {{VOCAB}}.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
