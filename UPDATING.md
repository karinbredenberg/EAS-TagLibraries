# Updating Tag Libraries

## Overview

Starting with EAD3 1.1.0, the standard will be updated with incremental changes as needed.  As such, the tag library will need to be updated accordingly to reflect the current state of the standard.  This document outlines the necessary updates and strategies that will be used to keep the tag libraries up to date in parallel with the standard.

## Versioning

Major versions of the tag library (e.g. `1.0.0`) will contain changes that are incompatible with older versions of the standard.  Examples of changes that merit a major version include: removing/renaming elements or attributes; incorporating new conceptual models; invalidating existing examples of a schema.

Minor versions of the tag library (e.g. `1.1.0`) will contain changes that are compatible with existing versions of the standard.  Examples of changes that merit a minor version include: new elements/attributes; expanding value lists; adding new parent/child relationships between elements/attributes.

Editorial versions of the tag library (e.g. `1.1.1`) will contain no changes to the standard itself, but may include changes to the language of the tag library.  Examples of changes that merit an editorial version include: clarifying language used in the tag library; fixing typographical errors.  As Editorial versions will not include substantiative changes to the standard itself, certain steps in the updating procedure will be skipped.

## Title Pages

The title `type="additional"` must be updated to reflect the current version of the tag library in the `titleStmt` and `docTitle` elements.  The note element of `titlePage` must be updated to reflect the current version (e.g. "This tag library represents version EAD 1.1.0 [...].  It supersedes the Version 1.0.0 [...]").

## Preface

The preface must be updated with a revision-specific preface, titled "Preface to Revision _[version]_", if the current version if either Major or Minor.  This preface should include a brief description of the revision period (revision timeframe, comment periods, etc.) and a narrative of the changes made to the standard.  This will offer an overview of how and what changed in the current version of the tag library.

Version prefaces should be appended after the main preface, but before all other version prefaces.  From beginning to end, the prefaces should read in order of:

* _Primary preface_
* _Most recent version_
* _Second most recent version_
* _[...]_

## Inline Changes

Remove all existing inline change markers "(revised in _[previous version]_)" from the tag library if the current version is either Major or Minor.  At the end of each line in which a change was made to the text of the tag library, add "(revised in [version])" to the text.  This provides an easily-searchable point by which to search the text for updates, and flags changes for readers encountering them as they go.  Note that an element/attribute may appear multiple times throughout the tag library - for example, attributes may appear within entries in Elements and Attributes sections of the tag library.

If major changes are made to the text, such as a new element, change markers can be added at a higher level.  For example, new elements should receive a change marker in the `div type="fullName"` element, even though changes have been made to multiple lines below that element.

## Changelog

A running changelog has been added to the end of the EAD3 tag library.  This section replicates the information provided in the [RELEASE.md](https://github.com/SAA-SDT/EAD3/blob/master/RELEASE.md) for EAD3; in other words, a bulleted/numbered list of changes made since the last release.  Each release’s changelog must be appended to the beginning of the section and dated.

The purpose of the changelog is to provide a running list of changes made to the standard since 1.0.0.  Readers of the tag library can refer to the changelog for historic information on the text, as well as having the most recent changes enumerated in one place.

## Checklist

Before submitting a pull request to the [tag library repository](https://github.com/SAA-SDT/EAS-TagLibraries), verify that the following changes have been made:

1. References to the current revision of the tag library have had their version numbers updated
2. "Preface to Version x.y.z" has been added for the current version for Major and Minor versions
3. "(revised in x.y.z)" notes have been added to all instances across the tag library in which a changed attribute/element are listed
4. Last version’s "(revised in x.y.z)" notes have been removed across the text if the current version is either Major or Minor
5. Appropriate variables and namespaces have been set in the transformation XSLT documents
6. PDF and HTML documents have been generated from the revised TEI document