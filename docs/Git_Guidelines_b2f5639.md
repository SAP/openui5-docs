<!-- loiob2f563900ed2492b9b9003560e00ea9d -->

| loio |
| -----|
| b2f563900ed2492b9b9003560e00ea9d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/b2f563900ed2492b9b9003560e00ea9d) | [demo kit latest release](https://sdk.openui5.org/topic/b2f563900ed2492b9b9003560e00ea9d)</div>

## Git Guidelines

For using Git for developing content for OpenUI5, rules and guidelines for the use of Git and the content of commit messages have been introduced.

Set the `core.autocrlf` configuration property in Git to `false` and make sure to use Unix-style linebreaks \(LR-only\).

***

### Commit Message

The commit message consists of two or three parts, which are separated by empty lines:

-   Commit summary

-   Description

-   Data section


***

#### Commit Summary

The summary should be 50-70 characters long.

The summary line must be prefixed with either `[FIX]` or `[FEATURE]`, which should be followed by the control or component that is the main subject of the change.

Instead of `[FIX]` or `[FEATURE]` and at any other location in the commit message, you can use `[INTERNAL]` for commits or explanations which should not be part of the change log. If you add `[INTERNAL]` as only prefix to the commit message, the entire message won't be part of the change log. If you add this prefix to the middle of the message, everything after this prefix will be ignored for the change log.

Do not use any `[` or `]` within the summary but for the prefixes.

***

#### Description

Describe the problem you fix with this change. Whether your patch is a one-line bug fix or 5000 lines of a new feature, there must be an underlying problem that motivated you to do this work. Make the necessity of the fix clear to the reviewers, so they will continue reading.

Describe the effect that this change has from a user's point of view. App crashes and lockups are pretty convincing for example, but not all bugs are that obvious and should be mentioned in the text. Even if the problem was spotted during code review, describe the impact you think it can have on users.

After that, describe the technical details of what you changed. It is important to describe the change in a most understandable way so the reviewer is able to verify that the code is behaving as you intend it to.

***

#### Data section

The data section consists of name-value pairs:

-   `Fixes: https://github.com/SAP/openui5/issues/(issueNumber)` if the change fixes a GitHub-reported bug

-   `Closes: https://github.com/SAP/openui5/pull/(pullRequestNumber)` if the change comes from a pull request. This is usually added by the OpenUI5 committer handling the pull request

-   `Change-Id` for Gerrit


***

```html
[FIX] sap.m.Popover: scrolling is removed after Popover is rerendered

- this was caused by the special treatment in dealing with rerendering
in Popover.

- Now the normal invalidation is used and Popup.js takes care of the
focus/blur event listener in onBefore/AfterRerendering

Change-Id: I3c7d6e4d52fa71e9412b729b7a234a112915c2a4
Fixes: https://github.com/SAP/openui5/issues/1
```

