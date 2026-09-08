---
trigger: always_on
---

# Android (Kotlin) Rules

## Coding Instructions
- Language Stack: Modern Kotlin (Context receivers, explicit backing properties), Jetpack Compose, Kotlin Coroutines, and Asynchronous Flows.
- Architecture: Clean Architecture with MVI (Model-View-Intent) or strict MVVM state patterns. 
- UI State: UI components must only subscribe to single, immutable UI State flows emitted by ViewModels. State updates must be completely predictable and unidirectional.

## TDD & Testing Rules
- Red-Green-Refactor: Generate domain use-case unit tests before implementing UI or repository code.
- Concurrency Testing: Enforce strict usage of `TestDispatcher` and `runTest` blocks for testing Coroutines and Flows.
- Test Stack: MockK for behavior mocking, JUnit 5 for unit logic, and Compose UI Automated Tests (`createComposeRule`) for interface validation. 

## Productivity Mode
- Boilerplate Elimination: Leverage Kotlin features like extension functions, custom modifiers, and standard library operators (`run`, `let`, `apply`) to keep architecture concise but readable.
- Automated DI Mapping: Assume dependency injection via Hilt or Koin is pre-configured. Provide necessary module definitions explicitly when adding new classes.

## Output Optimization
- Layout: Group Android responses clearly by layer: 
  1. `domain/usecase/` 
  2. `data/repository/` 
  3. `presentation/viewmodel/` and `presentation/ui/`.
- No Shortcuts: All Jetpack Compose Previews and UI components must explicitly show state parameter passing. No hardcoded string literals—always mock out String resources.
