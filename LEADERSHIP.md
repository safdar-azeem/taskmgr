## Project Leadership & Technical Guidance

This document serves as the comprehensive guide for leading, mentoring, and scaling the MERN Task Management System. It provides detailed strategies for code review, developer mentoring, architectural decisions, and system scaling.

---

## 📋 Table of Contents

1. [Mentoring Plan](https://www.google.com/search?q=%23mentoring-plan)
2. [Code Review Approach](https://www.google.com/search?q=%23code-review-approach)
3. [Architecture Decisions](https://www.google.com/search?q=%23architecture-decisions)
4. [Scaling Strategy](https://www.google.com/search?q=%23scaling-strategy)
5. [Potential Improvements](https://www.google.com/search?q=%23potential-improvements)

---

## 👨‍🏫 Mentoring Plan

### Philosophy

Our mentoring approach is built on these core principles:

-   **Growth-Oriented**: Every task is a learning opportunity
-   **Hands-On**: Learn by doing with proper guidance
-   **Feedback-Rich**: Regular, constructive feedback loops
-   **Safe Environment**: Mistakes are learning opportunities
-   **Progressive Complexity**: Start simple, gradually increase difficulty

---

### Onboarding Process for Junior Developers

#### **Week 1: Environment & Fundamentals**

**Day 1-2: Setup & Introduction**

```
Goals:
- Set up complete development environment
- Understand project structure
- Run application locally (both frontend & backend)

Tasks:
1. Install Node.js 20+, MongoDB, Redis
2. Clone both repositories (taskmgr-client, taskmgr-api)
3. Install dependencies: npm install
4. Configure .env files
5. Start both applications successfully
6. Create a "Hello World" component/endpoint

```

```
Mentor Activities:
- Pair programming session for setup
- Explain project architecture (30-minute overview)
- Share architecture diagrams
- Assign a "buddy" for questions

Success Metrics:
✅ Application runs locally without errors
✅ Can make a simple code change and see results
✅ Understands folder structure at high level

```

**Day 3-4: Codebase Exploration**

```
Goals:
- Understand code organization
- Learn existing patterns
- Identify key files and their purposes

Tasks:
1. Read through README files thoroughly
2. Trace a complete user flow (e.g., Login → Dashboard → Create Task)
3. Document the flow in your own words
4. Create a simple diagram showing component relationships

Study Areas:
Frontend:
- /src/modules structure
- How routes work (routes/index.tsx)
- State management (store/useAuthStore.ts)
- API calls (lib/axios.ts)

Backend:
- MVC pattern (models, controllers, routes)
- Middleware flow (middleware/auth.middleware.ts)
- Database models (models/*.model.ts)
- API response patterns (utils/ApiFeatures.ts)

```

```
Mentor Activities:
- Daily 15-minute check-ins
- Answer questions about code patterns
- Provide additional context on design decisions

Deliverable:
📄 A 1-page document explaining one complete feature flow

```

**Day 5: First Contribution**

```
Goal: Make your first successful pull request

Task: Fix a "good-first-issue" bug
Example: "Fix typo in error message when email is invalid"

Steps:
1. Find issue in GitHub Issues (labeled "good-first-issue")
2. Create feature branch: git checkout -b fix/issue-123
3. Make the change
4. Write/update tests
5. Commit: git commit -m "fix: correct validation error message for email"
6. Push and create PR
7. Address review comments
8. Celebrate merge! 🎉


[Image of Git feature branch workflow diagram]

Mentor Review Focus:
- Git workflow understanding
- Commit message format
- Basic code quality
- Test coverage

Success Metrics:
✅ PR created with proper format
✅ All CI checks pass
✅ Responds to feedback constructively
✅ PR merged successfully

```

#### **Week 2: Feature Development Basics**

**Days 1-3: Small Feature Implementation**

```
Goal: Implement a self-contained, low-risk feature

Example Feature: "Add character counter to task description field"

Requirements:
- Show "X/500 characters" below textarea
- Turn red when approaching limit
- Prevent submission when over limit
- Add unit tests
- Update documentation

Learning Objectives:
✅ Component development
✅ State management
✅ Form validation
✅ Testing practices
✅ Documentation

Mentor Support:
- Initial design review (30 min)
- Mid-point check-in
- Code review with detailed feedback
- Pair programming if stuck > 2 hours

Expected Timeline:
Day 1: Design & setup (2-3 hours)
Day 2: Implementation (4-5 hours)
Day 3: Testing & refinement (2-3 hours)

```

**Days 4-5: Bug Investigation**

```
Goal: Learn debugging techniques

Task: Investigate and fix a real bug
Example: "Task filter doesn't reset when switching teams"

Debugging Process:
1. Reproduce the bug locally
2. Add console.logs to trace execution
3. Identify root cause
4. Implement fix
5. Add regression test
6. Document findings

Skills Developed:
✅ Problem-solving methodology
✅ Browser DevTools usage
✅ React DevTools proficiency
✅ Network tab analysis
✅ Test-driven bug fixing

Mentor Activities:
- Teach debugging techniques
- Review debugging approach
- Discuss root cause analysis
- Explain how to prevent similar bugs

Deliverable:
📝 Bug report document with:
- Steps to reproduce
- Root cause explanation
- Fix implemented
- Prevention strategy

```

#### **Week 3-4: Full Feature Ownership**

**Complex Feature Implementation**

```
Goal: Own a feature from design to deployment

Example Feature: "Task Comments System"

Phases:
1. Requirements Gathering (Day 1)
   - Read user stories
   - Ask clarifying questions
   - Create acceptance criteria

2. Design (Day 2)
   - Design API endpoints
   - Design database schema
   - Design UI components
   - Get design review approval

```

```
3. Implementation (Days 3-6)
   Backend:
   - Create Comment model
   - Add CRUD endpoints
   - Add validation & error handling
   - Write integration tests

   Frontend:
   - Create CommentList component
   - Create CommentForm component
   - Integrate with API
   - Add loading/error states
   - Write component tests

4. Testing (Day 7)
   - Manual testing
   - Fix bugs found
   - Performance testing
   - Accessibility testing

5. Documentation & Deployment (Day 8)
   - Update API documentation
   - Update README
   - Create PR with detailed description
   - Deploy to staging
   - Demo to team

Learning Objectives:
✅ End-to-end feature development
✅ API design principles
✅ Database modeling
✅ Component architecture
✅ Testing strategies
✅ Documentation practices

Mentor Checkpoints:
- Day 1: Requirements review
- Day 2: Design review (critical!)
- Day 4: Mid-implementation check
- Day 7: Pre-PR review
- Day 8: Final review & deployment

Success Metrics:
✅ Feature works as specified
✅ Tests have >80% coverage
✅ Code review has <5 major comments
✅ Documentation is complete
✅ Successfully deployed to production

```

---

### Task Breakdown Strategy

#### **How to Break Down Large Tasks**

**Example: "Implement Team Dashboard with Analytics"**

**❌ Bad Breakdown (too large):**

```
1. Build team dashboard
2. Add analytics
3. Test everything

```

**✅ Good Breakdown (manageable chunks):**

```
Phase 1: Data Layer (Backend)
├── Task 1.1: Create analytics aggregation query
├── Task 1.2: Add GET /api/teams/:id/analytics endpoint
├── Task 1.3: Write integration tests for endpoint
└── Task 1.4: Deploy to staging & test

Phase 2: UI Components (Frontend)
├── Task 2.1: Create TeamAnalytics component skeleton
├── Task 2.2: Implement TaskCompletionChart sub-component
├── Task 2.3: Implement MemberActivityList sub-component
├── Task 2.4: Add loading/error states
└── Task 2.5: Write component tests

Phase 3: Integration
├── Task 3.1: Connect components to API
├── Task 3.2: Add data refresh functionality
├── Task 3.3: Optimize API calls (caching)
└── Task 3.4: Manual testing & bug fixes

Phase 4: Polish
├── Task 4.1: Add animations & transitions
├── Task 4.2: Responsive design testing
├── Task 4.3: Accessibility audit
└── Task 4.4: Documentation & deployment

Total: ~25 hours across 16 discrete tasks

```

**Key Principles:**

1. **Each task is 1-3 hours max** (prevents overwhelm)
2. **Tasks are testable** (clear definition of done)
3. **Dependencies are explicit** (Phase 1 before Phase 2)
4. **Incremental value** (each phase is deployable)
5. **Time estimates included** (helps planning)

#### **Daily Task Planning Template**

```
Junior Developer Daily Plan:

Morning (9 AM - 12 PM):
┌─────────────────────────────────────────────┐
│ Task: Implement TaskCompletionChart         │
│ Time: 3 hours                               │
│ Blockers: None identified                   │
│ Help needed: Chart library selection        │
│                                             │
│ Subtasks:                                   │
│ ☐ Research chart libraries (30 min)        │
│ ☐ Get mentor approval on library (15 min)  │
│ ☐ Implement basic chart (1.5 hours)        │
│ ☐ Add data formatting (45 min)             │
│ ☐ Add unit tests (30 min)                  │
└─────────────────────────────────────────────┘

Afternoon (1 PM - 5 PM):
┌─────────────────────────────────────────────┐
│ Task: Code review learning                  │
│ Time: 1 hour                                │
│ ☐ Review 2 PRs from team members            │
│ ☐ Leave comments/questions                  │
│ ☐ Learn new patterns used                   │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Task: Bug fix - Filter reset issue          │
│ Time: 2 hours                               │
│ ☐ Reproduce bug (30 min)                    │
│ ☐ Debug & identify root cause (1 hour)     │
│ ☐ Implement fix (30 min)                    │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Task: Learning time                         │
│ Time: 1 hour                                │
│ ☐ Read TypeScript documentation             │
│ ☐ Watch team's recorded tech talk           │
└─────────────────────────────────────────────┘

End of Day:
☐ Update ticket status in Jira
☐ Push code to feature branch
☐ Write tomorrow's plan
☐ Post standup update

```

---

### Review Process

#### **Code Review Stages**

**Stage 1: Self-Review (Before Submitting PR)**

```
Checklist for Junior Developer:

Functionality:
☐ Does it work as expected?
☐ Tested manually with different inputs
☐ Edge cases handled
☐ Error cases handled

Code Quality:
☐ Removed all console.logs
☐ Removed commented-out code
☐ No hardcoded values (use constants)
☐ Meaningful variable names
☐ Functions are small (<50 lines)
☐ No duplicate code

Testing:
☐ Unit tests added/updated
☐ All tests pass locally
☐ Test coverage >80%

Standards:
☐ Follows naming conventions
☐ Follows file structure patterns
☐ TypeScript types defined properly
☐ No 'any' types used

Documentation:
☐ JSDoc comments for public functions
☐ README updated if needed
☐ Complex logic explained in comments

Git:
☐ Commit messages follow format
☐ Single responsibility per commit
☐ PR description is detailed
☐ Linked to issue/ticket

```

**Stage 2: Peer Review**

```
Timeline: Within 24 hours

Another junior or mid-level developer reviews:
- Basic functionality
- Code readability
- Test coverage
- Obvious bugs

Feedback Example:
"Hey! Nice work on this feature. A few observations:
1. Line 45: Consider extracting this logic into a helper function
2. The loading state isn't handled - what if API is slow?
3. Tests look good! Maybe add one for error case?"

Goal: Collaborative learning, catching obvious issues

```

**Stage 3: Senior Review**

```
Timeline: Within 48 hours

Senior developer or tech lead reviews:
- Architecture alignment
- Performance implications
- Security concerns
- Best practices adherence

This is the PRIMARY learning opportunity!

```

**Stage 4: Post-Merge Review**

```
Timeline: Next 1-on-1 meeting

Discuss:
- What went well?
- What was challenging?
- What would you do differently?
- What did you learn?

This solidifies learning and builds confidence.

```

#### **1-on-1 Meeting Structure (Weekly, 30 minutes)**

```
Agenda Template:

1. Personal Check-in (5 min)
   - How are you feeling about your progress?
   - Any concerns or blockers?
   - Work-life balance okay?

2. Technical Growth (10 min)
   - Review code from past week
   - Discuss patterns learned
   - Explain design decisions made
   - Questions on codebase

3. Current Work (10 min)
   - Review current task progress
   - Unblock any issues
   - Discuss approach/design
   - Pair program if needed

4. Growth Planning (5 min)
   - Set learning goal for next week
   - Identify skill gaps
   - Recommend resources
   - Plan next challenge

Action Items:
- Junior: Document learnings in personal wiki
- Mentor: Follow up on blockers
- Both: Schedule pair programming if needed

```

---

### Growth Strategy

#### **Skill Progression Path**

```
Month 1: Foundation
├── Week 1: Environment & Setup
├── Week 2: Simple Bug Fixes
├── Week 3: Small Features
└── Week 4: First Complex Feature
    Skills: Git, React basics, API basics, Testing basics

Month 2: Proficiency
├── Week 5: Performance Optimization
├── Week 6: State Management Mastery
├── Week 7: Advanced TypeScript
└── Week 8: Database Optimization
    Skills: Advanced React patterns, Mongoose, Redis, Performance

Month 3: Ownership
├── Week 9: Lead Small Feature (with guidance)
├── Week 10: Architectural Decisions (with input)
├── Week 11: Code Review Others' Work
└── Week 12: Production Debugging
    Skills: Architecture, Leadership, Mentoring, Operations

Month 4-6: Independence
├── Own features end-to-end
├── Mentor new junior developers
├── Participate in design discussions
└── Lead small technical initiatives
    Skills: Full-stack ownership, Technical leadership

Month 7-12: Senior Junior (transitioning to mid-level)
├── Lead medium-sized projects
├── Make architectural proposals
├── Conduct technical interviews
└── Present at team tech talks
    Skills: System design, Team leadership, Communication

```

#### **Learning Resources by Topic**

```
React & Frontend:
Week 1-2: React Official Docs (new docs.react.dev)
Week 3-4: TypeScript Handbook
Week 5-6: Advanced React Patterns (patterns.dev)
Week 7-8: Performance Optimization (web.dev)

Backend & Database:
Week 1-2: Node.js Best Practices (github.com/goldbergyoni)
Week 3-4: Express.js Guide
Week 5-6: MongoDB University Course
Week 7-8: Redis Documentation

System Design:
Week 9-10: System Design Primer
Week 11-12: Designing Data-Intensive Applications (book)

Soft Skills:
Ongoing: How to Win Friends and Influence People
Ongoing: The Pragmatic Programmer
Ongoing: Clean Code (Robert Martin)

```

#### **Quarterly Growth Reviews**

```
Review Template:

Technical Skills Assessment:
┌──────────────────────────┬─────────┬─────────┬──────────┐
│ Skill                    │ Q1      │ Q2      │ Target   │
├──────────────────────────┼─────────┼─────────┼──────────┤
│ React                    │ ★★☆☆☆   │ ★★★★☆   │ ★★★★★    │
│ TypeScript               │ ★★☆☆☆   │ ★★★☆☆   │ ★★★★☆    │
│ Node.js/Express          │ ★☆☆☆☆   │ ★★★☆☆   │ ★★★★☆    │
│ MongoDB/Mongoose         │ ★☆☆☆☆   │ ★★☆☆☆   │ ★★★★☆    │
│ Testing (Jest)           │ ★★☆☆☆   │ ★★★☆☆   │ ★★★★☆    │
│ Git/GitHub               │ ★★☆☆☆   │ ★★★★☆   │ ★★★★★    │
│ System Design            │ ☆☆☆☆☆   │ ★☆☆☆☆   │ ★★★☆☆    │
│ Code Review              │ ★☆☆☆☆   │ ★★★☆☆   │ ★★★★☆    │
└──────────────────────────┴─────────┴─────────┴──────────┘

Achievements This Quarter:
✅ Successfully launched Task Comments feature
✅ Reduced bug count by 40% through better testing
✅ Mentored 1 new junior developer
✅ Presented tech talk on React performance

Goals for Next Quarter:
🎯 Lead Team Analytics Dashboard feature
🎯 Learn advanced MongoDB aggregation pipelines
🎯 Contribute to architecture decision for caching layer
🎯 Improve code review turnaround time to <12 hours

Feedback from Team:
"Great progress on React! Focus more on backend skills next quarter."
"Really appreciated your thorough code reviews."
"Keep asking questions - shows strong curiosity!"

```

---

## 🔍 Code Review Approach

### Philosophy

Code review is the MOST IMPORTANT mentoring tool. It should be:

-   **Educational**: Teach, don't just critique
-   **Constructive**: Suggest improvements, not just problems
-   **Specific**: Provide examples and alternatives
-   **Encouraging**: Acknowledge good work
-   **Timely**: Review within 24 hours

---

### Review Priority Framework

#### **P0: Blocking Issues (Must Fix Before Merge)**

**1. Security Vulnerabilities**

```typescript
// ❌ CRITICAL: SQL/NoSQL Injection
const user = await User.findOne({
  email: req.body.email // Unsanitized input!
})

// ✅ CORRECT: Use mongoose validation + sanitization
const email = validator.isEmail(req.body.email)
  ? req.body.email.toLowerCase()
  : null
if (!email) return next(new AppError('Invalid email', 400))
const user = await User.findOne({ email })

Review Comment:
"🚨 SECURITY: This endpoint is vulnerable to NoSQL injection.
An attacker could pass:
  { "email": { "$ne": null } }
and bypass authentication.

Fix: Add input validation and use express-mongo-sanitize middleware.
See: middleware/auth.middleware.ts for example.
```

```typescript
// ❌ CRITICAL: Exposed sensitive data
app.get('/api/users', async (req, res) => {
  const users = await User.find()
  res.json(users) // Returns passwords, OTPs, etc!
})

// ✅ CORRECT: Select only safe fields
app.get('/api/users', async (req, res) => {
  const users = await User.find().select('name email avatar')
  res.json({ data: { users } })
})

Review Comment:
"🚨 SECURITY: This exposes sensitive user data including hashed passwords
and OTPs. Even hashed, this is a security risk.

Fix: Always use .select() to explicitly choose safe fields.
Better: Create a user.toPublicJSON() method for consistent serialization.

Example in user.model.ts:
userSchema.methods.toPublicJSON = function() {
  return {
    id: this._id,
    name: this.name,
    email: this.email,
    avatar: this.avatar
  }
}"

```

```typescript
// ❌ CRITICAL: XSS Vulnerability
<div dangerouslySetInnerHTML={{ __html: user.bio }} />

// ✅ CORRECT: Sanitize or don't use dangerouslySetInnerHTML
import DOMPurify from 'dompurify'
<div dangerouslySetInnerHTML={{
  __html: DOMPurify.sanitize(user.bio)
}} />

// ✅ BETTER: Just render as text
<div>{user.bio}</div>

Review Comment:
"🚨 SECURITY: XSS vulnerability! User-controlled content rendered as HTML.
An attacker could inject:
  <script>steal_cookies()</script>

Fix Options:
1. (Best) Remove dangerouslySetInnerHTML, render as text
2. (If HTML needed) Use DOMPurify to sanitize
3. (Backend) Sanitize on save with xss-clean

```

**2. Data Loss Risks**

```typescript
// ❌ CRITICAL: No error handling - data could be lost
app.post('/api/tasks', async (req, res) => {
  const task = await Task.create(req.body)
  res.json(task)
  // What if database fails? User gets error but no retry!
})

// ✅ CORRECT: Proper error handling
app.post('/api/tasks', async (req, res, next) => {
  try {
    const task = await Task.create(req.body)
    res.status(201).json({
      status: 'success',
      data: { task }
    })
  } catch (error) {
    console.error('Task creation failed:', error)
    return next(new AppError('Failed to create task', 500))
  }
})

Review Comment:
"⚠️ DATA RISK: If database fails, we return 500 but user's data is lost.

Issues:
1. No try-catch means unhandled promise rejection
2. No logging makes debugging impossible
3. User has no way to retry

Fix: Use catchAsync wrapper (utils/catchAsync.ts) and proper error handling.

Also consider:
- Validation before DB call (fail fast)
- Idempotency for retries (use unique request IDs)
- Transaction if multiple DB operations"

```

**3. Breaking Changes**

```typescript
// ❌ BREAKING: Changed API response format
// Old: res.json({ tasks: [...] })
// New: res.json({ data: { tasks: [...] } })

Review Comment:
"🚨 BREAKING CHANGE: This alters the API contract!

Impact:
- Frontend will break (expecting tasks directly)
- Mobile app will break
- Any external integrations will break

Required steps:
1. Version the API: /api/v2/tasks
2. Keep v1 endpoint working
3. Update all clients to use v2
4. Deprecate v1 after 3 months
5. Update API documentation

```

---

#### **P1: Important Issues (Should Fix)**

**1. Performance Problems**

```typescript
// ❌ N+1 Query Problem
const tasks = await Task.find({ teamId })
for (const task of tasks) {
	task.assignee = await User.findById(task.assignedTo) // N queries!
}

// ✅ CORRECT: Use populate
const tasks = await Task.find({ teamId }).populate(
	'assignedTo',
	'name email avatar'
)
```

```typescript
Review Comment:
"⚡ PERFORMANCE: N+1 query problem detected.

Current behavior:
- 1 query to get 100 tasks
- 100 queries to get each assignee
- Total: 101 database queries!

Fix: Use Mongoose populate() for a single join query.

Impact:
- Before: ~500ms for 100 tasks
- After: ~50ms for 100 tasks
- 10x improvement! ✨

```

```typescript
// ❌ No pagination - loads all records
const tasks = await Task.find({ user: req.user._id })

// ✅ CORRECT: Implement pagination
const page = parseInt(req.query.page) || 1
const limit = parseInt(req.query.limit) || 10
const skip = (page - 1) * limit

const tasks = await Task.find({ user: req.user._id })
  .limit(limit)
  .skip(skip)

Review Comment:
"⚡ PERFORMANCE: No pagination means loading ALL tasks.

Problem:
- User with 10,000 tasks = 10,000 records loaded
- Frontend freezes during rendering
- Wastes bandwidth

Fix: Use our ApiFeatures class (utils/apiFeatures.ts).

Example:
const { data, pageInfo } = await new ApiFeatures(Task, req.query)
  .filter()
  .sort()
  .paginate()
  .execute()

This handles pagination, sorting, filtering automatically!"

```

```typescript
// ❌ Unnecessary re-renders
const TaskList = ({ tasks }) => {
  const filteredTasks = tasks.filter(t => t.status === 'active')
  // This runs on EVERY render!

  return <div>{filteredTasks.map(...)}</div>
}

// ✅ CORRECT: Use useMemo
const TaskList = ({ tasks }) => {
  const filteredTasks = useMemo(
    () => tasks.filter(t => t.status === 'active'),
    [tasks] // Only recompute when tasks change
  )

  return <div>{filteredTasks.map(...)}</div>
}

Review Comment:
"⚡ PERFORMANCE: Expensive filter runs on every render.

Current: If parent re-renders (even for unrelated state), this filters again.
With 1000 tasks, this causes lag.

Fix: Use useMemo to memoize the result.

When to use useMemo:
✅ Expensive computations (filtering, sorting, mapping large arrays)
✅ Creating objects/arrays passed as props
❌ Simple operations (a + b)
❌ Already fast operations

React DevTools Profiler can show you the impact!"

```

**2. Error Handling Gaps**

```typescript
// ❌ Silent failure
const updateTask = async (id, data) => {
  try {
    await api.put(`/tasks/${id}`, data)
  } catch (error) {
    // Error silently swallowed!
  }
}

// ✅ CORRECT: Handle and inform user
const updateTask = async (id, data) => {
  try {
    const result = await api.put(`/tasks/${id}`, data)
    toast.success('Task updated successfully')
    return result.data
  } catch (error) {
    console.error('Task update failed:', error)
    toast.error(error.response?.data?.message || 'Failed to update task')
    throw error // Re-throw for caller to handle
  }
}

Review Comment:
"❗ ERROR HANDLING: Errors are silently swallowed!

Problems:
1. User doesn't know if update succeeded
2. No logging for debugging
3. Caller can't react to failure

Fix:
- Log errors for debugging
- Show user-friendly toast/alert
- Re-throw or return error state

Best practice: Use our useToast hook consistently:
const { showSuccess, showError } = useToast()

Also consider:
- Retry logic for network errors
- Offline detection
- Error boundaries for React errors"

```

**3. Missing Tests**

```typescript
// ❌ Complex logic without tests
export const calculateProjectProgress = (tasks) => {
  const completed = tasks.filter(t => t.status === 'done').length
  const total = tasks.length
  const percentage = (completed / total) * 100

  if (percentage >= 100) return { status: 'complete', progress: 100 }
  if (percentage >= 75) return { status: 'nearly-done', progress: percentage }
  if (percentage >= 50) return { status: 'on-track', progress: percentage }
  return { status: 'at-risk', progress: percentage }
}

Review Comment:
"🧪 TESTING: Complex business logic without tests!

This function has:
- 4 different code paths (edge cases)
- Mathematical calculations (prone to bugs)
- Business rules (could change)

Required tests:
1. All tasks complete (100%)
2. Nearly complete (75-99%)
3. On track (50-74%)
4. At risk (0-49%)
5. Edge: Empty array (0 tasks)
6. Edge: Single task
7. Edge: All tasks not done

Example test structure:
describe('calculateProjectProgress', () => {
  it('returns complete when all tasks done', () => {
    const tasks = [
      { status: 'done' },
      { status: 'done' }
    ]
    expect(calculateProjectProgress(tasks)).toEqual({
      status: 'complete',
      progress: 100
    })
  })

  // ... more tests
})

Run: npm test -- calculateProjectProgress.test.ts"

```

---

#### **P2: Nice-to-Have Improvements (Suggest)**

**1. Code Readability**

```typescript
// ❌ Hard to understand
const x = tasks.filter(t => t.s === 'a').map(t => ({...t, u: t.u || {}}))

// ✅ BETTER: Descriptive names
const activeTasks = tasks
  .filter(task => task.status === 'active')
  .map(task => ({
    ...task,
    assignee: task.assignee || {}
  }))

Review Comment:
"💡 READABILITY: Variable names are unclear.

This works, but future developers (including you in 6 months!)
will struggle to understand it.

Suggestions:
- Use descriptive names (task vs t, status vs s)
- Extract to named function if complex
- Add comment explaining the 'why'

Good naming is one of the hardest parts of programming!
Resources:
- 'Clean Code' by Robert Martin (Chapter 2)
- Our style guide: docs/style-guide.md"

```

```typescript
// ❌ Magic numbers
if (user.loginAttempts > 5) {
  user.lockAccount()
}
setTimeout(() => resetCache(), 300000)

// ✅ BETTER: Named constants
const MAX_LOGIN_ATTEMPTS = 5
const CACHE_TTL_MS = 5 * 60 * 1000 // 5 minutes

if (user.loginAttempts > MAX_LOGIN_ATTEMPTS) {
  user.lockAccount()
}
setTimeout(() => resetCache(), CACHE_TTL_MS)

Review Comment:
"💡 READABILITY: Magic numbers make code harder to maintain.

Questions future developers will have:
- Why 5? Why not 3 or 10?
- What's 300000? Seconds? Milliseconds?

Fix: Extract to named constants (top of file or constants.ts).

Benefits:
- Self-documenting code
- Single place to change values
- Easier"

```

**Built with ❤️ by Safdar Azeem**
