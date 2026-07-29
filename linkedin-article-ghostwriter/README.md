# linkedin-article-ghostwriter

Writes a finished long-form LinkedIn article from a developed content idea, in a
named person's voice, against approved company positioning and channel rules.

In a `marketing-agent-system` project it reads `.agent-context/INDEX.md` through
the shared context protocol before writing. It uses approved audience, author
voice, lead frame, proof points, banned terms, anti-AI writing rules, and
LinkedIn channel rules when those exist. The old fill-in configuration is now a
fallback for projects that have not set up `.agent-context/` yet.

The output is an article, not a short post: headline, dek, structured body,
method or application, proof-aware argument, objection handling, clean ending,
word count, and context note. It may draft for human approval, but it must not
publish or schedule the article.
