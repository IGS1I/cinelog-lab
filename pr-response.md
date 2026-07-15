# PR Response Doc — CineLog Watchlist Feature

## AI Usage
<!-- Fill in at the end — how you used AI tools during this project -->

## Comment 1 — Rename
**What I did:** I renamed function and function calls for save_to_watchlis() to add_to_watchlist().
**How I verified:** I verified the renaming was thorough by searching for the old name (save_to_watchlist) throughout the codebase on feature/watchlist branch.

## Comment 2 — Deduplication
**What I did:** I added the same deduplication logic from add_to_collection() to add_to_watchlist(). Another error was added called AlreadyInWatchlistError for the deduplication scenario where a user tries to add a film to their watchlist and the same film had already been added.
**How I verified:** Deduplication correction was tested using a newly added test "test_add_to_watchlist_duplicate_raises", added to tests/test_watchlist.py. Test passed.

## Comment 3 — Missing test
**What I did:** Created file tests/test_watchlist.py and pulled over logic from tests/test_collection.py. Tests that were added are test_add_to_watchlist_duplicate_raises() and test_add_to_watchlist_nonexistent_film_raises().
**How I verified:** Tests verified by running them. They both passed.

## Comment 4 — Default visibility
**My position:** The default public visibility is a valid decision.
**Reasoning:** These watchlists can be private if chosen as such, but CineLog is much more of a useful tool if friends and family can also see what you have watched or intend to watch. Leaving the visibility public by default is not a security issue therefore, sharable film lists become much more desireable.
**Tradeoff acknowledged:** Anyone can view your list meaning you can not hide the films you have watched or intend to watch, unless you delete the film entry.

## Comment 5 — Sort order
**My position:** I agree with the maintainer, watchlists should be sorted defaultly by date added, rather than alphabetical order.
**Reasoning:** This is the best decision for users that frequently check their watchlist to see what to watch next. They will be greeted with what they recently added, which works even better if the user adds films, watches the ones added, and adds some more films. The user can chronologically look at what they have been attempting to watch and, in their head, know which from the list has already been seen.
**Engagement with reviewer's point:** I completely agree with the reviewer/maintainer.

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->