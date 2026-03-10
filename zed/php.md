When generating PHP code, follow these language-specific rules.

Modern Standards: Always use PHP 8.3+ features. Leverage array destructuring, closures, arrow functions, match statements, and named arguments where appropriate to keep the codebase clean.

Style Guide: Follow PSR-12 coding standards, modified to use tabs for indentation.

Visibility: Default to protected access over private access.

Pragmatic Validation: Avoid overly strict "belt and braces" handling unless strict validation is requested. 
  - Use `$value = $array['key'] ?? ''` without `trim()` or type casting.
  - Use `empty($value)` checks instead of explicit `=== ''` chains.
  - Do not include `declare(strict_types=1);`.

Docblock Typing: Define additional typing in doc comments where appropriate (e.g., `/** @var PostOneshotResponse $response */`).
