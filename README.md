Copyright (c) 2026 Liam

This project is licensed under the MIT License. See the LICENSE file for details.
# FamilySearch-Tree-Exporter
A Chrome extension that lets you export your currently open FamilySearch family tree to a GEDCOM file with a single click.

## How it works

- It collects the person IDs of the people shown on the page, using the person links on the cards. It takes the starting person from the page URL.
- It then asks FamilySearch’s own ancestry data, using your logged-in session, for those people’s names, sexes, birth and death details. It keeps only the ones that appear on your page.
- Parent and child links are built from the pedigree numbering (a person’s father is 2n and mother is 2n+1), so the GEDCOM has proper family records.
- It adds no extra ancestors and does no searching.

## Known limits

- Marriage dates and places aren’t included, only birth and death.
- It reaches at most 8 generations back.
- FamilySearch can change how its page and API work. If you get “No person cards found” or an HTTP error, send me the HTML of one person card (right-click a card, then Inspect, then Copy outerHTML) and the exact error text, and I’ll fix the selectors. Ticking “Ignore page filter” exports everything the ancestry data returns, which is a quick way to test whether the data part works.
