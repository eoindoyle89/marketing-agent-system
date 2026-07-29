# linkedin-post-reviewer

A ten-principle gate that runs before a LinkedIn post ships. Each principle has
a named test that can't be waved through — read the first two lines only, would
the configured reader stop scrolling? Cover everything below the first
paragraph, what is this post about now? Each returns PASS, FAIL, or BORDERLINE,
and every FAIL comes back with the offending line quoted and replacement text
written. It checks audience, lead frame, voice authenticity, buried product
pitches, hook strength, ending, banned language, and dialect.

It exists because the failure mode of ghostwritten content isn't bad writing.
Bad writing is easy to catch. The failure mode is writing that sounds on-brand
while quietly leading with the wrong frame, or landing a pitch in the last line
where it reads as a conclusion. This reviewer is for short LinkedIn posts; the
long-form `linkedin-article-ghostwriter` needs a separate article review pass.
