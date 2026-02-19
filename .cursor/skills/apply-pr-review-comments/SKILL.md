---
name: apply-pr-review-comments
description: Applies pull request review comments to documentation changes. Accepts strict commands (+, -, frase corretta: [...]) or clear human phrasings (e.g. Mantenere, Eliminare, Rimuovere). Use when a reviewer leaves PR comments and the user asks to apply or sync requested edits from GitHub review threads.
---

# Apply PR Review Comments

Use this skill to apply review feedback from GitHub PR comments. The skill accepts both **strict commands** and **clear human phrasings** when the action is unambiguous.

## Scope

- This skill is for documentation and text edits in PR files.
- Do not guess reviewer intent when the comment is vague.
- Accept comments that are clearly understandable in terms of the action to perform.

## Accepted Comment Commands

Each review comment must express exactly one actionable instruction. Two forms are accepted:

### Forma breve (preferita)

- `+`
- `-`
- `frase corretta: [...]`

### Equivalenti comprensibili

Quando il commento è una frase ma l’azione è inequivocabile, trattala come il comando corrispondente:

| Intenzione | Comando | Frasi accettate (esempi) |
|------------|---------|---------------------------|
| Mantieni / ripristina la riga | `+` | **Mantenere**, Mantieni, Tenere, Keep, Restore, Sì |
| Rimuovi / non tenere la riga | `-` | **Eliminare**, Rimuovere, Togliere, Remove, Delete, No |
| Sostituisci con testo dato | `frase corretta: [X]` | **frase corretta: [testo]** (obbligatoria la parentesi quadra con il testo) |

- Confronto **case-insensitive** e ignorando spazi in eccesso.

## Interpretation Rules

Usa la posizione del commento nel diff della PR (riga aggiunta = verde, riga rimossa = rosso). Le stesse regole valgono sia per i comandi brevi (`+`/`-`) sia per le frasi equivalenti (es. Mantenere → come `+`, Eliminare → come `-`).

- **Commento su riga aggiunta (verde):**
  - `+` / Mantenere / Mantieni / ecc. → mantieni la riga aggiunta
  - `-` / Eliminare / Rimuovere / ecc. → rimuovi la riga aggiunta
  - `frase corretta: [...]` → sostituisci la riga con il testo indicato

- **Commento su riga rimossa (rossa):**
  - `+` / Mantenere / Mantieni / ecc. → ripristina la riga rimossa
  - `-` / Eliminare / Rimuovere / ecc. → lascia la riga rimossa (nessuna modifica)

Se il comando è in conflitto con lo stato attuale del file (riga spostata, modificata o assente), usa il blocco non ambiguo più vicino nello stesso file e segnala che serve verifica manuale.

## PR Selection Default

When the user asks to check comments without specifying a PR:

1. Scan all open PRs in the repository.
2. For each PR, collect review comments and issue comments.
3. Keep only PRs with actionable comments (sintassi supportata o frasi equivalenti comprensibili).
4. Report a summary:
   - total open PRs scanned
   - PRs with actionable comments
   - number of actionable comments per PR

Apply actions **without asking for confirmation**: when the user asks to apply (or after reporting the summary), apply on all PRs that have actionable comments. If multiple PRs are involved, process them in PR number order.

## Workflow

1. Identify PR(s) and target branch(es) using the default selection rules above.
2. Retrieve comments and filter only unresolved comments with valid commands.
3. Group actions by file, then apply in a stable order (top-to-bottom in each file).
4. Re-check diffs for accidental side effects.
5. Commit with a message referencing review feedback.
6. Push to the PR branch.
7. Reply on each handled thread with a short status message and resolve when appropriate.

## Safety Rules

- Never apply ambiguous comments.
- Never modify unrelated files.
- Never change behavior outside reviewer-requested lines.
- If two comments conflict on the same line, stop and ask the user which one wins.
- If the reviewer asks both "keep old" and "remove new" for the same hunk, treat as a revert to old text.

## Thread Reply Template

For each processed comment, use:

- `Applicato: comando "<cmd>" eseguito su questa riga.`

For skipped comments, use:

- `Saltato: commento non riconducibile a un'azione univoca (accettate: +, -, frase corretta: [...], o equivalenti come Mantenere/Eliminare/Rimuovere).`

## Commit Message Template

Use:

- `docs: apply PR review comments`

Optional body:

- `Applied structured reviewer commands (+, -, frase corretta) from PR threads.`

## Quick Checklist

- [ ] Parsed only supported commands o equivalenti comprensibili
- [ ] Applied changes only on commented files/lines
- [ ] Verified resulting diff is minimal
- [ ] Pushed to the same PR branch
- [ ] Replied and resolved handled threads

