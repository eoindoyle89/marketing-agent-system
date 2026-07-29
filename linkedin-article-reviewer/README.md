# linkedin-article-reviewer

A twelve-principle gate that runs before a long-form LinkedIn article ships.
It is the article-length counterpart to `linkedin-post-reviewer`: same
philosophy, higher bar, because an article asks for minutes of attention
rather than a scroll-stop.

Each principle has a named test — walk the section headings alone, do they
form an argument? State the thesis without "and", can you? Find the strongest
skeptic's objection, is it actually answered? Each returns PASS, FAIL, or
BORDERLINE, and every FAIL comes back with the offending text quoted and a
replacement written. It checks audience commitment, lead frame, headline and
dek, thesis discipline, structure, method, proof boundaries, objections,
author voice and territory, pitch drift, ending, and banned language.

It reads `.agent-context/INDEX.md` through the shared context protocol before
reviewing, so audience, voice, lead frame, and approved claims come from the
company store, not from the skill. It may fail an article; it must not
publish one.
