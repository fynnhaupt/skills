# Track review status in PR labels

The agent opens PRs under the user's GitHub login, so the user is the author and can't request, approve, or reject a review on them; GitHub's native review states stay empty. Review status therefore lives in `status: …` labels on the PR, and the task issue carries a status only until its PR opens, so no status is kept in two places.
