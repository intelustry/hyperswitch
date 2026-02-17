# Hyperswitch API Documentation Guide for Claude

## Project Overview

This is the API reference documentation for **Hyperswitch**, an open-source payments infrastructure built in Rust. The documentation covers comprehensive payment processing APIs, including payments, refunds, customers, payment methods, disputes, and more.

## Documentation Structure

- **Format**: MDX (Markdown with JSX components)
- **Platform**: Mintlify
- **Location**: `/api-reference/` directory
- **Versioning**: Two major versions (v1 and v2)
- **Configuration**: `docs.json` for navigation and settings

## File Organization

```
api-reference/
├── docs.json                 # Main configuration
├── introduction.mdx          # Getting started page
├── essentials/              # Core documentation
├── v1/                      # Version 1 API endpoints
│   ├── payments/
│   ├── refunds/
│   ├── customers/
│   └── ...
├── v2/                      # Version 2 API endpoints (BETA)
├── locker-api-reference/    # Card vault APIs
├── intelligent-router-api-reference/
└── _snippets/              # Reusable content
```

## Content Standards

### Writing Style

1. **Clarity First**: Write clear, concise explanations suitable for both beginners and experienced developers
2. **Active Voice**: Use active voice when possible
3. **Present Tense**: Describe features in present tense
4. **Consistency**: Maintain consistent terminology throughout

### Formatting Guidelines

1. **Headings**: Use sentence case (capitalize only the first word)
2. **Code Blocks**: Always specify language for syntax highlighting
3. **API Endpoints**: Format as: `POST /payments`
4. **Field Names**: Use backticks for field/parameter names (e.g., `payment_id`)
5. **Values**: Use backticks for specific values (e.g., `"automatic"`)

### MDX Components

Common Mintlify components used in this documentation:

- `<Tip>`: For helpful hints and best practices
- `<Warning>`: For important warnings
- `<Info>`: For general information
- `<Note>`: For additional context
- `<Steps>`: For step-by-step instructions
- `<Step>`: Individual step within Steps
- `<Tooltip>`: For inline explanations
- `<CodeGroup>`: For multi-language code examples

### API Documentation Pattern

Each API endpoint file follows this structure:

```mdx
---
openapi: post /endpoint-path
---
<Tip> Optional helpful tip about the endpoint </Tip>
```

The `openapi` frontmatter automatically pulls in the API specification from the OpenAPI schema files.

## Technical Details

### Payment Flow Terminology

- **Payment Intent**: The initial payment object
- **Confirm**: Finalizing a payment
- **Capture**: Settling an authorized payment
- **CIT**: Customer Initiated Transaction
- **MIT**: Merchant Initiated Transaction
- **PSP**: Payment Service Provider

### Status Values

Common payment statuses:
- `succeeded`: Payment completed successfully
- `requires_capture`: Authorization successful, awaiting capture
- `requires_payment_method`: Needs payment method
- `processing`: In progress
- `failed`: Payment failed

## Contributing Guidelines

### When Updating Documentation

1. **Verify Accuracy**: Ensure all technical details match the current API implementation
2. **Test Examples**: Verify code examples work correctly
3. **Check Links**: Ensure all internal links are valid
4. **Update Both Versions**: If a feature exists in both v1 and v2, update both
5. **Maintain Consistency**: Keep terminology and formatting consistent across pages

### Code Examples

When adding code examples:
- Provide realistic, working examples
- Include all required fields
- Use placeholder values that are clearly identifiable (e.g., `"your-api-key"`)
- Show both request and response when helpful
- Use JSON formatting for REST APIs

### Diagrams

- Use Mermaid for sequence diagrams and flowcharts
- Keep diagrams simple and focused
- Add clear labels and descriptions

## Common Tasks

### Adding a New API Endpoint

1. Create `.mdx` file in appropriate version directory
2. Add frontmatter with `openapi` reference
3. Add to navigation in `docs.json`
4. Include helpful tips or examples if needed

### Updating Navigation

Edit `docs.json` → `navigation.tabs` → find version → update `pages` array

### Creating Reusable Content

Create files in `_snippets/` directory and import as MDX components

## Quality Checklist

Before finalizing any documentation update:

- [ ] Technical accuracy verified
- [ ] Consistent terminology used
- [ ] Code examples tested
- [ ] Links validated
- [ ] Proper MDX components used
- [ ] Formatting follows guidelines
- [ ] Version-specific content marked clearly
- [ ] No broken references

## Resources

- Main repo: https://github.com/juspay/hyperswitch
- Live documentation: Hosted on Mintlify
- Slack community: https://inviter.co/hyperswitch-slack

## Notes for Claude

When working with this documentation:

1. **Preserve OpenAPI references**: Don't remove or modify the `openapi` frontmatter
2. **Respect versioning**: v2 is BETA, make this clear in any v2 content
3. **Use established patterns**: Follow existing examples in similar files
4. **Test context**: Consider both sandbox and self-deploy scenarios
5. **Business context**: Hyperswitch serves enterprises and developers building payment systems
