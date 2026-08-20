# Contributing

Contributions welcome. To add a new problem, improve existing content, or
fix errors:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Submit a pull request

## Style guide

- Every design pattern doc should include: intent, a real (not toy) use
  case, a code example in at least one language, and when *not* to use
  the pattern — overuse of design patterns is a real anti-pattern worth
  naming explicitly.
- LLD problems follow the same shape: requirements → class design →
  key relationships → code sketch → what we'd do differently.
- Concurrency content must be technically precise — this is the category
  where hand-wavy explanations do the most damage, since subtle
  concurrency bugs are exactly what these docs are trying to prevent.

If you find this resource helpful, please give it a star and share it
with others.
