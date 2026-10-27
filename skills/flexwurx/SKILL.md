---
name: flexwurx
description: Judgment for working with FlexWurx's contract and insurance compliance data through the FlexWurx connector's tools. Use whenever those tools are available and the user asks about their contracts, tenants, vendors, properties, insurance requirements or compliance, or wants a document query run across their contracts.
---

# Working with FlexWurx

FlexWurx holds the contracts and insurance compliance records of the organizations the signed-in user can access: the organizations themselves, their properties, tenants and subs (vendors), and each contract's stored text. Every tool covers only what this user can see, and every result names the organization it belongs to.

What each tool does is in its own description. This skill is about judgment: how to use the tools well. It doesn't set an order of calls. Decide which tools a question needs, and in what order, from the question itself.

## When the entity is unclear, ask

Names repeat. The same name can belong to more than one entity, a vendor can be linked to several organizations, and the search tolerates typos, so a name often finds more than one candidate. When a name could be more than one entity, ask the user which one they mean before reading anything, and offer the candidates the search found as the options. Reading the wrong tenant's contracts gives a confident, wrong answer.

## Read a contract whole

One contract is small enough to read whole, so read it rather than searching inside it. A search finds the words it was asked for. Reading finds the clause that changes them: an exception two pages later, an amendment, a definition that narrows a term.

## Unsure which search fits? Run both

Keyword search finds exact words, numbers and names: a policy number, a dollar amount, a set phrase. Meaning search finds a passage about an idea however it's worded, such as who pays for repairs after a fire. Each misses what the other finds, so when it's unclear which one a question needs, run both.

## A search hit is a lead, not an answer

A snippet or a passage shows where something might be. Read the page before answering from it. The sentence around a match often qualifies it, and a matching passage can belong to a different party or an old version of the contract.

## Cite the contract and the page

For every answer drawn from a contract, name the contract and the page, so the user can check it. When the contract is an old version, say so.

## Get a document query right before starting it

A document query has a model read every contract it covers, and each contract costs a model call. So:

- Settle the instructions and the fields with the user before starting, so the run answers what they actually need.
- Don't rerun a query to make small tweaks. Get it right once.
- When the user can access more than one organization, as a brokerage user can, confirm which one the query is for. A run covers one organization.

A run keeps going after it starts, and one over a few hundred contracts can take 10 to 20 minutes. After starting one, keep calling query_status until the run finishes or fails: each call waits up to 30 seconds for it, then says how far it has got. Between calls, give the user a one-line progress update, such as "12 of 40 contracts read so far." Once it has finished, page through the results. If the user asks for the results so far while it's still going, ask query_status for them; that call doesn't wait.

## Look at the page image when the text isn't enough

The stored text comes from OCR. Look at the page image when the text looks garbled, or when handwriting, initials, signatures or checkboxes on the page matter to the answer. A struck-through clause, an initialed change or an unchecked box can reverse what the text seems to say.

## When a contract's text isn't stored yet

Some contracts are still being processed. When a contract's text isn't stored yet, tell the user so, rather than answering without it. When a contract has no file attached, say so: there's no text to read until someone attaches one. A contract entered by hand has no document and never will; say that instead.
