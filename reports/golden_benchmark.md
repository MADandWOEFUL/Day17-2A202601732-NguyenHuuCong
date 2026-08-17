# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1436.2 ms**
- Average token reduction vs full source context: **14.5%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.5 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.1 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1844.5 | 864 | 0.0% |  |
| G09 | semantic | PASS | 263.6 | 148 | 67.8% |  |
| G10 | semantic | PASS | 371.8 | 95 | 79.3% |  |
| G14 | mixed | PASS | 2523.5 | 431 | 0.0% |  |
| G03 | long_term | PASS | 1532.6 | 1437 | 0.0% |  |
| G04 | long_term | PASS | 1426.4 | 1437 | 0.0% |  |
| G07 | episodic | PASS | 440.8 | 627 | 0.0% |  |
| G08 | episodic | PASS | 487.1 | 639 | 0.0% |  |
| G11 | mixed | PASS | 2448.6 | 439 | 22.3% |  |
| G13 | mixed | PASS | 817.2 | 406 | 28.1% |  |
| G15 | mixed | PASS | 2561.1 | 736 | 0.0% |  |
| G16 | mixed | PASS | 2351.6 | 484 | 14.3% |  |
| G17 | mixed | PASS | 2250.1 | 484 | 14.3% |  |
| G18 | mixed | PASS | 607.7 | 403 | 28.7% |  |
| G19 | mixed | PASS | 1847.5 | 581 | 0.0% |  |
| G05 | long_term | PASS | 1965.2 | 1434 | 0.0% |  |
| G12 | mixed | PASS | 2321.8 | 431 | 31.8% |  |
| G20 | mixed | PASS | 2662.4 | 609 | 3.6% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`<USER_SUMMARY> Lan Tran's main project is LOTUS-88. They prioritize Java and Spring Boot for backend development.  Lan prefers to use Java and Spring Boot and explicitly does not use Python for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 10:07:26     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Minh la Lan, phap ly hoi gat truoc khi bat memory tren san pham. Viet hop dong ngan: backend minh dang dung ngon ngu/framework nao, va quy tac luu/xoa bo nho ca nhan trong lab yeu cau opt-in va v`

### G09 - semantic

`EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.`

### G10 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.`

### G14 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan Tran's main project is LOTUS-88. They prioritize Java and Spring Boot for backend development.  Lan prefers to use Java and Spring Boot and explicitly does not use Python for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Ass`

### G03 - long_term

`<USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short examples. Minh is c`

### G04 - long_term

`<USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short examples. Minh is c`

### G07 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngo`

### G08 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Pyt`

### G11 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G13 - mixed

`<EPISODIC> EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python. EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can`

### G15 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G18 - mixed

`<EPISODIC> EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van `

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G05 - long_term

`<USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short examples. Minh is c`

### G12 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh is working on a personal project called ORCHID-27, for which Python is preferred. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used. Minh is also debugging async HTTP requests related to connection churn (ASYNC-FIX-20) and is investigating the connection pool, client lifecycle, and concurrency. Minh found that reusing an aiohttp ClientSession with a concurrency of 20 resolves connection churn issues. Minh needs to complete a benchmark report labeled LAB-REPORT-1600 for ORCHID-27 before Friday at 4 PM.  Minh prefers Python and dislikes Java. When explaining code, Minh wants the AI to use short example`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
