---
trigger: always_on
---

# iOS (Swift) Rules

## Coding Instructions
- Language Stack: Modern Swift, SwiftUI exclusively, native Async/Await concurrency patterns.
- Architecture: Clean Architecture paired with Unidirectional Data Flow (UDF) or Observable ViewModels. 
- State Engine: Leverage modern Swift features such as the `@Observable` macro for reactive UI rendering instead of legacy `ObservableObject` paradigms.

## TDD & Testing Rules
- Red-Green-Refactor: Write `XCTestCase` code verifying business state transitions before designing SwiftUI views.
- Concurrency Isolation: Every unit test asserting async methods must implement proper isolation using Swift Actors and structured concurrency tools.
- Test Stack: Native `XCTest` framework. Avoid external testing libraries unless explicitly requested.

## Productivity Mode
- Modern Swift Paradigms: Maximize the use of Swift's Type-Safe KeyPaths, Generics, and protocol extensions to eliminate duplication across repositories and ViewModels.
- UI Scalability: Structure SwiftUI components into small, modular sub-views utilizing `@ViewBuilder` to ensure low cognitive load and hyper-optimized compile times.

## Output Optimization
- Execution: Always output the core protocol-based interfaces (Interactors/Repositories) first to lay the swift contract down, followed directly by the Unit Tests, and finally the SwiftUI implementations.
- No Truncation: Provide full definitions for UI views, mock data models for previews, and complete async closures. Never inject placeholder comments into network pipelines.
