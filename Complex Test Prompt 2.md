# Complex Multi-Agent Test Prompt #2 for Alexis

## Test Scenario: Emergency Financial Decision + Planning Session

**User Request:**
"Alexis, I'm in a bit of a situation and need your help with multiple things urgently. My laptop just died and I need a replacement ASAP for work. Can you research current prices for business laptops under €800 in Brussels - check both new and refurbished options at places like MediaMarkt, Fnac, and Back Market? I also need to know store hours for MediaMarkt Heyzel and Fnac City 2 since I want to visit tomorrow. 

Meanwhile, I just realized I forgot to log several expenses from this week: €85 for groceries on Monday, €23 for lunch with clients on Tuesday, and €156 for that work dinner on Wednesday. After you log those, I need to see my current account balance and check if I have enough to buy a €650 laptop without going below €200 (my emergency fund minimum).

Oh, and I keep forgetting to set up my recurring payments - can you schedule my monthly phone bill of €45 starting next month for the next 12 months? Also research current iPhone 15 Pro prices because mine is getting old and I might upgrade if there are good deals.

Finally, show me how much I've spent on work-related meals this month and whether I'm close to my €300 business dining limit."

## Expected Behavior Analysis:

### 1. Goal Identification (11 distinct goals):
1. Research business laptops under €800 (new) → **Internet Research Agent**
2. Research refurbished laptops → **Internet Research Agent**  
3. Research MediaMarkt Heyzel hours → **Internet Research Agent**
4. Research Fnac City 2 hours → **Internet Research Agent**
5. Log €85 groceries expense → **Ledger Agent**
6. Log €23 client lunch expense → **Ledger Agent**
7. Log €156 work dinner expense → **Ledger Agent**
8. Check current account balance → **Data Analyst Agent**
9. Schedule recurring phone bill payments → **Ledger Agent**
10. Research iPhone 15 Pro prices → **Internet Research Agent**
11. Analyze work meal spending vs €300 budget → **Data Analyst Agent**

### 2. Expected Optimal Wave Structure:

**Wave 1 (Parallel) - Start with independent goals:**
- Ledger Agent: Log €85 groceries expense (Monday)
- Internet Research Agent: Research business laptops under €800 (new options)
- Data Analyst Agent: Analyze work meal spending vs €300 budget
- Send interim message: "Got it! That's a lot to handle - let me process your expenses and start researching those laptop options..."

**Wave 2 (Parallel):**
- Ledger Agent: Log €23 client lunch expense (Tuesday)
- Internet Research Agent: Research refurbished laptop options

**Wave 3 (Parallel):**
- Ledger Agent: Log €156 work dinner expense (Wednesday)  
- Internet Research Agent: Research MediaMarkt Heyzel hours

**Wave 4:**
- Internet Research Agent: Research Fnac City 2 hours

**Wave 5 (Parallel):**
- Ledger Agent: Schedule recurring phone bill (€45 × 12 months)
- Internet Research Agent: Research iPhone 15 Pro prices

**Wave 6:**
- Data Analyst Agent: Check current account balance and affordability analysis

### 3. Advanced Testing Points:

**✅ Context Prioritization:**
- Should recognize urgency ("ASAP for work", "tomorrow")
- Balance immediate needs vs routine tasks

**✅ Logical Dependencies:**
- Must log expenses BEFORE checking balance for accurate affordability
- Store hours research can be parallel to expense logging

**✅ Complex Financial Analysis:**
- Account balance check with specific constraint (€200 minimum)
- Budget analysis for specific category (work meals vs €300 limit)

**✅ Professional Communication:**
- Handle urgent tone appropriately
- Clean company names: "MediaMarkt", "Back Market", "Fnac" 
- Embedded links for all research results
- Currency formatting: *€650*, *€200*, *€45*

**✅ Comprehensive Synthesis:**
- Emergency laptop situation addressed first
- All routine tasks completed
- Clear financial guidance provided

## Alternative High-Complexity Test Scenarios:

### Scenario B: "Multi-Context Image Analysis"
*User sends image of receipt*
"I can't read this receipt clearly - what did I buy and for how much? Log whatever expenses you can identify, then research if any of these items have current deals or better prices elsewhere. Also, I think one item might be wrong - research return policies for this store."

**Expected:** Image analysis → expense logging → price research → policy research

### Scenario C: "Financial Planning Emergency"
"My rent is due tomorrow and I'm not sure if I have enough! Check my balance, look for any pending transactions I might have missed, research emergency loan options with good rates in Belgium, and see if I can transfer money from my savings. If I'm short, calculate exactly how much I need and find the cheapest way to get it quickly."

**Expected:** Complex dependency chain with emergency financial analysis

### Scenario D: "Investment Research Session"
"I want to start investing €200 monthly. Research current best investment platforms in Belgium, compare their fees, look up beginner-friendly index funds, and check what the average returns have been. Then log this month's €200 investment intent and see if this fits my budget after all my current expenses."

**Expected:** Heavy research load with financial integration

## Success Indicators:

1. **Smart Wave Distribution:** 6 sequential waves optimized for efficiency
2. **Priority Recognition:** Laptop urgency addressed early in synthesis  
3. **Dependency Management:** Expenses logged before balance check
4. **Professional Tone:** Matches user's urgent but business context
5. **Complete Coverage:** All 11 goals addressed systematically
6. **Clean Presentation:** Store names without domains, embedded links

## Potential Failure Points:

❌ **Overwhelm Response:** Breaking down into too many micro-tasks
❌ **Priority Confusion:** Not recognizing laptop urgency 
❌ **Race Conditions:** Checking balance before logging all expenses
❌ **Communication Breakdown:** Raw URLs, broken formatting under stress
❌ **Agent Overload:** Too many parallel calls to same agent type

This scenario tests Alexis under pressure with mixed urgent/routine tasks while maintaining professional multi-agent coordination.