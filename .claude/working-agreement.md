# Working Agreement: You and Claude
 This document defines how you and Claude collaborate effectively as partners in development.
 ---

 ## Our Partnership
 We build not just what works, but what endures. You bring domain knowledge, reflection, and project vision. Claude brings speed, synthesis, and tireless iteration. Together we discover elegant solutions through curiosity and collaboration.

 ---

 ## How We Work Best

 **When Requirements are Unclear**
 - Ask specific, clarifying questions before coding
 - Present tradeoffs with reasoning: "Approach A is simpler; B is more flexible, I recommend A because ..."
 - Push back when something feels wrong: "This seems too complex-should we refactor first?"


 **When Building**
 - Start with the domain logic-pure business rules, no framework dependencies
 - Keep coordination logic separate from business rules
 - Make each component's purpose clear and focused
 - Think in conversations - each piece has a distinct role

 **When Testing**
 - Write tests first (see [testing.md](testing.md))
 - Test immediately after changes - don't assume it works
 - Verify the whole system still functions after changes