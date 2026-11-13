# Yusuf Kenan Akgün

**Backend engineer — C# / ASP.NET Core · PostgreSQL · Python**
Istanbul, Turkey · B.Sc. Computer Engineering, Yeditepe University (2026)

I build REST services where correctness lives in the schema rather than in
application code, and I measure what I ship instead of assuming it works.
Backend is where I'm deepest; I also own the React / React Native clients on
my own products.

---

## Products in production

Three products I took from requirements to the stores, with a small team —
system architecture, PostgreSQL data modelling, clients and release
engineering.

| | What it is |
|---|---|
| **[Jet Teslimat](https://jetteslimat.com.tr/)** | Two-sided courier marketplace — order state machine, payment flow, real-time courier state over WebSocket. ~500 active users. |
| **Hayrına** | Donation platform, zero to both app stores in one month. |
| **[ERL Peyzaj](https://erlpeyzaj.com/)** | Web + iOS platform with Redis caching and an S3 / Cloudinary media pipeline. ~5K web visitors. |

---

## Selected work

**[vocab-api](https://github.com/yusufkenanakgun/vocab-api)** — C# · ASP.NET Core · EF Core · PostgreSQL · JWT
Spaced-repetition REST service. A shared `Word` dictionary is split from
per-user progress, so a word is stored once but holds independent state for
every user — a composite unique index and a restricted delete keep those
rules in the schema, not in application code. BCrypt + HS256 JWT, with the
user resolved from the token's `sub` claim and never from the client.

**[rag-app](https://github.com/yusufkenanakgun/rag-app)** — Python · sentence-transformers
Retrieval-augmented question answering over my own thesis, written end to end
with no RAG framework and no vector database: over 339 chunks a single matrix
multiplication is the correct answer, and an infrastructure component would
have been an unmeasured complexity cost.

The part I care about is that it measures its own limit. hit@10 = 7/11,
hit@20 = 8/11. On 9 of 9 questions the thesis never answers, it refuses
rather than inventing. And the finding that matters: retrieval is **5/5 when
a question shares the thesis's wording and 1/5 when the same question is
paraphrased** — an encoder limit, not a `k` limit, which points at a stronger
embedding model or a reranking layer rather than at retrieving more chunks.

**[asl-recognition](https://github.com/yusufkenanakgun/asl-recognition)** — PyTorch · ONNX · TensorFlow Lite · Android
B.Sc. thesis: on-device sign language recognition framed as a deployability
comparison rather than an accuracy race. EfficientNet-B0 (4.1M params,
15.71 MB) against a landmark MLP over hand joints (60K params, 0.24 MB).

EfficientNet-B0 classified all 13,050 held-out images correctly — a 100% I
did not trust, so both models were retested without retraining on 870
external photos with different capturers, backgrounds and lighting. It fell
to 59.77% while the landmark model held 90.72%. Converted through ONNX to
TensorFlow Lite and measured on real hardware: on an entry-level phone only
the landmark MLP stays real-time (24.5 FPS / 21.7 ms); EfficientNet-B0 pays
203 ms end to end.

---

## Stack

**Backend** C#, ASP.NET Core, Entity Framework Core, Python, FastAPI, REST, JWT
**Data** PostgreSQL, Redis, SQL
**Frontend & mobile** React, TypeScript, JavaScript, React Native
**ML** PyTorch, ONNX, TensorFlow Lite, on-device inference, RAG, embeddings
**Tooling** Docker, Git, Azure DevOps

Previously a software engineering intern at Türkiye Finans Katılım Bankası
(IT Accounting), on C# / ASP.NET Core banking software under a Software
Architect.

---

📫 [yusufkenanakgun@gmail.com](mailto:yusufkenanakgun@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/yusuf-kenan-akg%C3%BCn-77152233a/)
