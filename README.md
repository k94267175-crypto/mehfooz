
# Mehfooz

A free scam-message checker for people in Pakistan. A user pastes a suspicious SMS or WhatsApp message written in Roman Urdu or Urdu. Mehfooz says whether it looks like a scam, why, and what to do next.

## Why

Fake BISP/Ehsaas prize money, "your JazzCash account is blocked" links, and requests for OTP or PIN are common in Pakistan. Most scam-check tools work only in English.

## How it works (current prototype)

- Runs fully in the browser. No message is sent or stored anywhere.
- Rule-based: it looks for warning signs such as requests for PIN/OTP/CNIC, surprise money, "contact us on WhatsApp", pressure to act fast, threats, payment before a prize, and links from unknown senders.
- Three verdicts: **Scam**, **Suspicious**, **No major warning signs found**.
- Gives up to three reasons in simple Roman Urdu and a next step.

## Testing so far

- 30 synthetic messages written by the author: 27 correct. The 3 misses are "suspicious" cases (a bill, a job offer, a sale) that rules cannot tell apart from normal messages.
- 6 real scam-style messages: the first version called 5 of them "safe". The shared pattern (fake BISP/Ehsaas money plus "contact us on WhatsApp") was added as rules, and all 6 are now caught. Because the rules were tuned on these messages, this is not a fair accuracy number. More fresh real messages are needed.

## Limits

- Rules miss new wording and misspellings.
- "No major warning signs" does not mean safe.
- Screenshot and voice-note checking are not built yet.
- Punjabi (Shahmukhi) support is thin.

## Planned

1. Add a language model for messages the rules miss.
2. Screenshot check (read text from an image).
3. Voice-note check (speech to text, then check).
4. Collect more real messages, with names, numbers and CNIC removed.

## Files

- `checker.js`: the rules and the scoring.
- `test_messages.json`: 30 synthetic test messages with expected labels.
- `run_tests.js`: runs the checker on the test messages.

## License

Add an open-source license file (for example MIT) before publishing.
