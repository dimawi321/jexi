# JEXI PROJECT CONTEXT

## WHAT JEXI IS

Jexi is a self-custody crypto payment memory and preparation tool.

Jexi helps users remember scheduled or recurring crypto payments, save trusted recipient profiles, view payment history, run transparent preflight checks, and prepare transactions for user-controlled approval.

Jexi does not automatically control a user's assets.

The core philosophy is:

AI/automation can remember.
AI/automation can prepare.
AI/automation can check.
AI/automation can explain.

But the user remains in control.

Critical asset actions must ultimately require explicit user approval through a secure signing mechanism, with Ledger hardware intended to become the primary security anchor.

Jexi must never require or store:

- Private keys
- Seed phrases
- Ledger PINs
- Sensitive wallet secrets

---

## THE PROBLEM

Crypto users may repeatedly send payments to the same people or addresses.

Examples include:

- Sending money to family
- Paying recurring subscriptions
- Sending monthly support
- Paying contributors
- Making regular stablecoin transfers

Remembering every payment manually is inconvenient.

At the same time, fully automatic crypto payments can remove user control and create security risks.

Jexi solves this by remembering and preparing payments without taking away final approval.

---

## THE CORE WORKFLOW

1. The user creates a recipient profile.

2. The user saves:

- Recipient name
- Wallet address
- Network
- Optional notes

3. The user creates a payment intention.

Example:

Pay Mum 50 USDC every month on the 25th.

4. Jexi remembers the schedule.

5. When the payment becomes due, Jexi prepares the payment for review.

6. Jexi runs transparent preflight checks.

7. The user reviews the transaction details.

8. The final critical action requires user-controlled approval.

9. The intended Ledger model is:

Jexi prepares → User reviews → Ledger displays → User physically approves → Ledger signs → Transaction broadcasts.

10. After confirmation, the transaction becomes part of the recipient's payment history.

---

## PRODUCT PHILOSOPHY

Jexi should remain:

- Focused
- Simple
- Useful
- Trustworthy
- Self-custodial
- Ledger-aligned

Jexi should NOT become:

- A crypto super app
- A wallet
- A portfolio tracker
- A trading platform
- A generic AI assistant
- A dashboard with unnecessary features

Every feature must support the central workflow:

Remember → Check → Prepare → User Approves.

---

## AGENT / AUTOMATION PHILOSOPHY

Jexi follows the principle:

Automation without delegated custody.

Automation may:

- Remember schedules
- Detect due payments
- Retrieve relevant information
- Compare payment details with historical patterns
- Run deterministic safety checks
- Prepare transaction data
- Explain warnings

Automation must NOT:

- Access private keys
- Access seed phrases
- Sign transactions
- Pretend a transaction was signed
- Pretend a transaction was broadcast
- Override the user's final decision

---

## PREFLIGHT CHECKS

The initial Jexi Preflight system should use deterministic rules and should not require a paid AI API.

Checks include:

### Amount check

Compare the current payment amount with previous payments.

Example:

Usual payment: 50 USDC

Current payment: 500 USDC

Warning:

This payment is significantly higher than your usual payment.

### Recipient check

Detect if the recipient address differs from the saved or historical address.

### Network check

Confirm the transaction is being prepared on the intended network.

### Token check

Confirm the intended token matches the payment intention.

### Balance check

Where possible, check whether the connected wallet appears to have sufficient balance before preparing the transaction.

AI may later help explain these results in natural language, but deterministic software must remain responsible for validation.

---

## PAYMENT STATES

Payments should use clear states:

- Scheduled
- Due
- Checking
- Ready for Review
- Awaiting Approval
- Signed
- Broadcast
- Confirmed

Alternative outcomes:

- Rejected
- Failed

The app must never falsely claim that a transaction was signed, broadcast, or confirmed.

---

## DATA MODEL

Jexi will eventually need these main categories:

### Users

Basic user identity and preferences.

### Recipients

Saved payment destinations.

Example:

Name: Mum

Network: Base

Wallet address: Saved address

### Payments

The user's payment intentions.

Example:

Recipient: Mum

Amount: 50

Token: USDC

Network: Base

Schedule: Monthly

### Transactions

Records of actual transaction outcomes.

Payments and transactions must remain separate.

A payment intention is not proof that a transaction happened.

---

## BLOCKCHAIN DIRECTION

The intended first blockchain environment is:

Base Sepolia testnet.

The intended first blockchain workflow is a test token transfer.

Jexi must eventually be architected so a transaction can be:

Prepared without signing → reviewed by the user → passed to a Ledger-compatible signing flow → signed only after hardware approval → broadcast → confirmed → recorded.

Development may initially use clearly labelled simulated transaction preparation.

Simulation must never be presented as Ledger signing or a real broadcast.

---

## BUDGET CONSTRAINT

The current MVP development budget is:

₦0.

The project should prioritize:

- Free tools
- Free tiers
- Open-source libraries
- Testnets
- No paid AI API dependency

Do not introduce a paid dependency unless explicitly approved.

---

## BACKUP STRATEGY

Jexi must never depend entirely on one AI coding platform.

The backup strategy is:

### Layer 1 — GitHub

GitHub is the master source code repository.

### Layer 2 — Project Context

This file explains the product and development state.

Any new AI coding agent should read this file before modifying the project.

### Layer 3 — Changelog

The project should maintain CHANGELOG.md recording major completed milestones and changes.

### Layer 4 — Periodic Backups

Important milestones should eventually be downloaded/exported as backup copies where practical.

---

## CURRENT DEVELOPMENT STATUS

Product direction: Complete.

Master product concept: Complete.

GitHub repository: Created.

Project context file: Being created.

No application code has been written yet.

No database has been created yet.

No blockchain connection has been created yet.

No Ledger integration has been created yet.

---

## CURRENT NEXT TASK

Create the initial Jexi application using a completely free, Android-friendly vibe-coding workflow.

Before modifying the application, any coding agent should:

1. Read this JEXI_PROJECT_CONTEXT.md file.
2. Understand the product philosophy.
3. Inspect existing code before changing anything.
4. Avoid rebuilding existing features.
5. Preserve the separation between transaction preparation and transaction authorization.

---

## NON-NEGOTIABLE SECURITY RULES

Never ask the user for:

- Seed phrase
- Private key
- Ledger recovery phrase
- Ledger PIN

Never store those values.

Never design server-side automatic signing.

Never give an AI agent signing authority.

Never represent simulated signing as Ledger signing.

Never represent an unsigned transaction as signed.

Never represent an unbroadcast transaction as broadcast.

The user must remain the final authority over asset movement.
