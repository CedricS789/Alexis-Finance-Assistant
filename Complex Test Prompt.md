# Complex Multi-Agent Test Prompt for Alexis

## Test Scenario: Multi-Goal Financial Planning & Research Session

**User Request:**
"Hey Alexis! I need help with several things for my monthly budget planning. First, log these expenses from yesterday: €45 for groceries at Carrefour, €12 for coffee at Starbucks, and €8 for parking downtown. Then I want to research current prices for a new laptop - specifically look up MacBook Air M3 13-inch prices in Belgium and also check what's available on the refurbished market like Back Market. After that, I need you to tell me how much I've spent on dining out this month and whether I'm staying within my €200 dining budget. Finally, research opening hours for MediaMarkt Brussels and Fnac Brussels because I want to visit both stores this weekend. Oh, and schedule my monthly gym membership payment of €35 for the next 6 months starting November 1st."

## Expected Alexis Behavior Analysis:

### 1. Goal Identification (8 distinct goals):
1. Log €45 groceries expense → **Ledger Agent**
2. Log €12 coffee expense → **Ledger Agent** 
3. Log €8 parking expense → **Ledger Agent**
4. Research MacBook Air M3 prices → **Internet Research Agent**
5. Research refurbished laptop market → **Internet Research Agent**
6. Analyze dining out spending vs budget → **Data Analyst Agent**
7. Research store hours (MediaMarkt) → **Internet Research Agent**
8. Research store hours (Fnac) → **Internet Research Agent**
9. Schedule recurring gym payments → **Ledger Agent**

### 2. Expected Wave Structure:

**Wave 1 (Parallel):**
- Ledger Agent: Log €45 groceries expense
- Internet Research Agent: Research MacBook Air M3 prices in Belgium
- Data Analyst Agent: Analyze dining out spending against €200 budget
- Send interim message: "Got it! Processing your expenses and researching that information..."

**Wave 2 (Parallel):**
- Ledger Agent: Log €12 coffee expense  
- Internet Research Agent: Research refurbished laptop options (Back Market focus)

**Wave 3 (Parallel):**
- Ledger Agent: Log €8 parking expense
- Internet Research Agent: Research MediaMarkt Brussels hours

**Wave 4:**
- Internet Research Agent: Research Fnac Brussels hours

**Wave 5:**
- Ledger Agent: Schedule recurring gym payments (€35 × 6 months)

### 3. Key Testing Points:

**✅ Proper Agent Routing:**
- Transaction logging → Ledger Agent
- Financial analysis → Data Analyst Agent  
- Real-time research → Internet Research Agent

**✅ Sequential Wave Management:**
- No parallel calls to same agent type
- Logical wave distribution
- Dependencies respected

**✅ Communication Standards:**
- Clean company names (no .be extensions)
- Embedded hyperlinks only
- Professional presentation
- Currency formatting: *€35*

**✅ Delegation Principles:**
- High-level goal delegation
- No micromanagement
- Trust specialists

## Alternative Complex Test Scenarios:

### Scenario A: "Transfer & Analysis Chain"
"Transfer €500 from Main to Savings, then tell me my new Savings balance and whether I can afford to buy a €300 PlayStation 5 - also research current PS5 prices and stock availability at Game Mania."

**Expected:** Sequential waves due to dependencies (transfer must complete before balance query)

### Scenario B: "Image Analysis + Research"
*User sends image of damaged iPhone*
"What's wrong with my phone and how much would it cost to repair? Also look up replacement costs for iPhone 14 Pro and check repair shops in Brussels."

**Expected:** Image analysis interpretation, followed by targeted research based on findings

### Scenario C: "Budget Planning Session"
"Show me my financial summary, then research prices for: Netflix subscription, Spotify Premium, Disney+ in Belgium. After that, log a €25 subscription expense for Netflix and tell me if adding all these subscriptions would fit my €100 entertainment budget."

**Expected:** Complex multi-wave coordination with financial analysis and multiple research goals

## Success Criteria:

1. **Proper Goal Decomposition:** 8-9 distinct goals identified
2. **Correct Agent Selection:** Each goal routed to appropriate specialist
3. **Wave Management:** Sequential waves, no parallel same-agent calls
4. **Clean Communication:** Professional language, embedded links, proper currency formatting
5. **Comprehensive Synthesis:** All results integrated into coherent final response
6. **User Experience:** Interim updates, no greetings in final response

## Expected Failure Points to Monitor:

❌ **Micromanagement:** Breaking down goals into sub-tasks
❌ **Parallel Same-Agent Calls:** Multiple Internet Research calls in one wave
❌ **Race Conditions:** Dependent goals in same wave
❌ **Fabricated Information:** URLs or prices not from research
❌ **Communication Issues:** Raw URLs, broken formatting, redundant links

This test will thoroughly validate Alexis's multi-agent orchestration capabilities and adherence to the refined system prompt principles.