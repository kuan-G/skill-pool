---
name: java-tech-vietnamese-keyword
description: Explain a Java Core, Spring, backend, or related technology keyword quickly in Vietnamese. Use when the user provides a keyword, concept, acronym, annotation, API, design pattern, JVM topic, database/cache/message-queue term, or interview topic and wants its Vietnamese meaning, a short explanation, and examples.
---

# Java Tech Vietnamese Keyword

## Goal

Return a concise Vietnamese explanation for one or more technical keywords. Optimize for quick understanding, interview review, and practical backend work.

## Input Handling

- Treat the user input as the keyword unless they explicitly ask for another format.
- If the input contains multiple keywords, answer each keyword separately with the same compact template.
- Prefer Java Core and Spring meanings when a keyword is ambiguous.
- If the keyword has multiple common meanings, list the most relevant meanings and state which one is usually meant in Java/Spring/backend context.
- If the keyword is not Java/Spring-specific but is related to backend engineering, explain it in that broader tech context.
- Keep the answer in Vietnamese. Keep English technical terms when they are the industry-standard term.

## Output Template

Use this structure by default:

```markdown
**Keyword:** `<keyword>`

**Cách phát âm:** <simple pronunciation hint for Vietnamese learners; keep it practical, e.g. `GEN-er-iks`, `strim API`, or `in-tơ-phây-s`>

**Nghĩa tiếng Việt:** <short Vietnamese meaning>

**Giải thích nhanh:** <2-4 sentences explaining what it is, why it exists, and where it appears in Java/Spring/backend systems.>

**Ví dụ:** <one small practical example, code snippet, or scenario>

**Cần nhớ:** <1-3 concise bullets with interview/practical notes, common confusion, or tradeoffs>
```

For very simple keywords, shorten the answer to 4 sections: `Cách phát âm`, `Nghĩa tiếng Việt`, `Giải thích nhanh`, `Ví dụ`.

For interview-style questions, add:

```markdown
**Câu trả lời phỏng vấn ngắn:** <2-4 sentence answer suitable for speaking aloud>
```

For comparison keywords such as `interface vs abstract class`, use:

```markdown
**So sánh nhanh**

| Tiêu chí | <A> | <B> |
|---|---|---|
| Mục đích | ... | ... |
| Khi dùng | ... | ... |
| Lưu ý | ... | ... |
```

## Explanation Rules

- After the keyword and pronunciation, give the direct Vietnamese meaning first.
- Include a practical pronunciation hint right after the keyword for English technical terms. Prefer easy-to-read Vietnamese-friendly pronunciation over formal IPA.
- Explain from simple to practical: definition -> purpose -> example.
- Avoid long theory unless the user asks for depth.
- Prefer examples familiar to Java backend work: REST API, service layer, repository, transaction, thread, JVM, Spring Bean, dependency injection, database query, cache, Kafka/RabbitMQ.
- For Java/Spring code examples, keep snippets minimal and syntactically plausible.
- Include common pitfalls when useful, especially for interview topics.
- Say "không nên dịch cứng" when a term is normally kept in English, then provide a natural Vietnamese interpretation.

## Example Outputs

### Input: `polymorphism`

**Keyword:** `polymorphism`

**Cách phát âm:** `po-li-MOR-fizm`

**Nghĩa tiếng Việt:** Tính đa hình.

**Giải thích nhanh:** Trong OOP, đa hình là khả năng một lời gọi method có thể chạy các implementation khác nhau tùy object thực tế. Trong Java, nó thường xuất hiện qua inheritance, interface, overriding và dynamic dispatch.

**Ví dụ:**

```java
Payment payment = new MomoPayment();
payment.pay(100_000);
```

Biến có type `Payment`, nhưng method `pay()` chạy logic của `MomoPayment`.

**Cần nhớ:**
- Overriding là nền tảng thường gặp của runtime polymorphism.
- Overloading là compile-time polymorphism, không giống overriding.

### Input: `@Transactional`

**Keyword:** `@Transactional`

**Cách phát âm:** `tran-ZAK-shơ-nồ`

**Nghĩa tiếng Việt:** Annotation khai báo phạm vi transaction.

**Giải thích nhanh:** Trong Spring, `@Transactional` giúp một method chạy trong một database transaction. Nếu method thành công thì commit, nếu gặp exception phù hợp thì rollback. Nó thường dùng ở service layer cho các thao tác ghi dữ liệu cần đảm bảo tính nhất quán.

**Ví dụ:**

```java
@Transactional
public void transfer(Long fromId, Long toId, BigDecimal amount) {
    debit(fromId, amount);
    credit(toId, amount);
}
```

**Cần nhớ:**
- Mặc định rollback với unchecked exception.
- Gọi method `@Transactional` nội bộ trong cùng class có thể không đi qua Spring proxy.
