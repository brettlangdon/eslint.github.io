---
title: Reviewing Pull Requests
layout: doc
---

# Reviewing Pull Requests

Pull requests are submitted frequently and represent our best opportunity to interact with the community. As such, it's important that pull requests are well-reviewed before being merged and that interactions on pull requests are positive.

## Who Can Review Pull Requests?

Anyone, both team members and the public, may leave comments on pull requests.

## Who Can Approve Pull Requests?

Only project reviewers or admins may use the "Merge" button to merge in changes.

## Reviewing a Pull Request

When a pull request is opened, follow these steps:

1. Has the submitter signed a CLA? If not, please ask them to do so.
1. Is the commit message summary in the correct format? Double-check that the tag ("Fix:", "New:", etc.) is correct based on the issue. Documentation-only pull requests do not require an issue.
1. Does the code follow our conventions (including header comments, JSDoc comments, etc.)? If not, please leave that feedback and reference the conventions document.
1. For code changes:
    * Are there tests that verify the change? If not, please ask for them.
    * Is documentation needed for the change? If yes, please let the submitter know.
1. Are there any automated testing errors? If yes, please ask the submitter to check on them.
1. If you've reviewed the pull request and there are no outstanding issues, leave a comment "LGTM" to indicate your approval. If you're a reviewer and would like someone else to verify the change, comment "LGTM but would like someone else to verify."

**Note:** If you are a team member and you've left a comment on the pull request, please follow up to verify that your comments have been addressed.

## When to Merge a Pull Request

If you are a reviewer, then you can click the "Merge" button on a pull request to merge the changes. Before merging a pull request, verify that:

1. All comments have been addressed.
1. Any team members who made comments have verified that their concerns were addressed.
1. All automated tests are passing (never merge a pull request with failing tests).

Ideally, the first reviewer to comment on the pull request should be the one to merge it. However, if you don't feel comfortable doing so for any reason, just leave a comment saying "LGTM but would like someone else to verify".

Be sure to say thank you to the submitter before merging, especially if they put a lot of work into the pull request.

## When to Close a Pull Request

There are several times when it's appropriate to close a pull request without merging:

1. The pull request addresses an issue that is already fixed
1. The pull request hasn't been updated in 30 days
1. The pull request submitter isn't willing to follow project guidelines.

In any of these cases, please be sure to leave a comment stating why the pull request is being closed.

### Example Closing Comments

If a pull request hasn't been updated in 30 days:

> Closing because there hasn't been activity for 30 days. If you're still interested in submitting this code, please feel free to resubmit.

If a pull request submitter isn't willing to follow project guidelines.

> Unfortunately, we can't accept pull requests that don't follow our guidelines. I'm going to close this pull request now, but if you'd like to resubmit following our guidelines, we'll be happy to review.

