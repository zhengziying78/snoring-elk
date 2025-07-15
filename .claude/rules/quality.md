# Quality Rules

## Code Quality Standards
- **No Magic Numbers/Strings**: Avoid magic numbers and magic strings
- **Comprehensive Renaming**: When renaming symbols (variables, enums, functions, etc.), do thorough search to ensure all references are updated, including both product code and test code

## Build and Testing Requirements
- **Default Testing**: When making code changes, by default you should also run build and tests
- **Fix Build Errors**: If there are any build errors or test failures, fix them without needing explicit request
- **Review Readiness**: When asking for review (reject/accept) of changes, ensure the changes have passed build and tests

## iOS-Specific Quality Standards
- All changes must compile successfully in Xcode
- All existing unit tests and UI tests must pass
- New functionality should have appropriate test coverage
- Code should follow established Swift patterns and conventions in the codebase
- Battery efficiency: Prioritize battery conservation for overnight recording - optimize audio processing, minimize background tasks, and efficient memory management
- Background audio: Ensure proper handling of audio session and background modes
- Privacy: Respect user privacy and explain permissions clearly 