    # Design Pattern Fundamentals

    ## Key Patterns to Know

    ### Composition over Inheritance
    - Build behavior by combining small pieces instead of extending big ones
    - **The Pitfall:**
        - Deep hierarchies
        - Tight coupling
        - Changes ripple everywhere
        - Multiple inheritance doesn't exist in JS

    ### Controlled vs Uncontrolled Components

    **Answers: Who owns the state?**

    #### Controlled Components
    Parent owns the state using `useState`
    - ✅ Single source of truth
    - ✅ Predictable
    - ✅ Easy validation
    - ✅ Easy to sync
    - ❌ More re-renders
    - ❌ More boilerplate

    #### Uncontrolled Components
    DOM owns the state (no `useState`)
    - ✅ Less re-renders
    - ✅ Less code
    - ❌ Harder to control

    #### When to Use Which
    - **Controlled:** Validation, live preview
    - **Uncontrolled:** Simple forms, performance-critical scenarios

    ### Lifting State
    Two or more components need the same state

    **Benefits:**
    - Single source of truth
    - Predictable updates
    - Easy to debug

    **Rule of Thumb:** State should live in the lowest common ancestor that needs it

    ### Separation of Concerns
    Each piece of code should have one clear responsibility

    ### Summary
    - **Composition** for flexibility
    - **Controlled** for predictability
    - **Uncontrolled** for performance
    - **Lifted states** for consistency
    - **Separation** for maintainability

    ## React Hygiene Rules

    ### Avoid Prop Drilling
    **Problem:** Passing props through components that don't need them to reach a deep child
    - Tight coupling
    - Fragile refactors
    - Hard to trace data flow
    - Components become prop pipes

    **Solutions:**
    - **Use Context:** Global data for auth user, theme, locale, feature flags
        - ⚠️ Avoid: Frequently changing values, large objects, all state everywhere
    - **Composition**

    ### Avoid Massive Components
    **Signs:**
    - Fetches data
    - Holds lots of state
    - Handles logic
    - Renders UI
    - Manages side effects

    **Solutions:**
    - Container/presentational pattern
    - Custom hooks
    - Compound components

    ### Keep Logic Out of JSX
    JSX is for describing UI, not doing work