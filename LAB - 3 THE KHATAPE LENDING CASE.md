# _LAB - 3_ 

## **<u>DIRECT ANSWER VS STEP-BY-STEP — THE KHATAPE LENDING CASE</u>** 

**Course:** BBA (FinTech) **Subject:** Generative AI / Prompt Engineering **Submitted by:** Himanshi **AI Tool Used:** ChatGPT 

## **STEP 1: READ AND UNDERSTAND THE KHATAPE CASE** 

#### **<mark>1.1 Introduction</mark>** 

KhataPe is a fictional digital lending company based in Indore. It provides small loans to kirana shop owners and college students through its mobile application. Every month, the company has a fixed lending budget and must choose between two loan products, Option A and Option B. 

Both options have different interest rates, processing fees, expected default rates and costs of funds. 

The Chief Financial Officer (CFO) wants to know whether AI can help the company select the more profitable loan option. The main objective of this lab is to compare two prompting methods: 

**Direct Answer Prompting:** Asking AI to provide only the final answer. 

**Step-by-Step Prompting:** Asking AI to calculate and explain each step before giving the final decision. 

#### **<mark>1.2 KhataPe's Decision Rules</mark>** 

The following rules are used to calculate the profitability of both loan options. Net Return Formula: 

Net Return = Interest Rate + Processing Fee − Expected Default − Cost of Funds Profit Formula: 

Profit = (Net Return ÷ 100) × Loan Budget Decision Rule: 

Choose the option that provides higher profit. 

If both options have equal profit, choose the option with the lower expected default. Operating costs, taxes and timing of payments are ignored. 

#### **<mark>1.3 Worked Example</mark>** 

Suppose KhataPe has a loan budget of ₹50 crore. 

##### **Option A:** 

Interest Rate = 22% 

Processing Fee = 2% Expected Default = 6% Cost of Funds = 10% 

Net Return = 22 + 2 − 6 − 10 = 8% Profit = 8 ÷ 100 × 50 = ₹4 crore 

**Option B:** 

Interest Rate = 18% Processing Fee = 1% Expected Default = 3% Cost of Funds = 10% Net Return = 18 + 1 − 3 − 10 = 6% Profit = 6 ÷ 100 × 50 = ₹3 crore 

**Final Decision:** KhataPe should select Option A because it provides higher profit. 

## **STEP 2: CREATE 8 LENDING SCENARIOS USING AI** 

### **<mark>2.1 Objective</mark>** 

The purpose of this step is to create eight fictional lending scenarios for KhataPe. These scenarios will be used to test whether AI can correctly compare the profitability of two loan options. 

The dataset includes three trap scenarios where the option with the higher interest rate makes less profit. It also includes one scenario where both options make exactly the same profit. 

#### **<mark>2.2 Prompt Used</mark>** 

You are helping me build a realistic test dataset for a business case study. 

KhataPe is a fictional digital lender in Indore. Every month it chooses between two loan products, Option A and I used the following prompt in ChatGPT: 

Option B. 

Create 8 monthly decision scenarios (S01 to S08). 

For each scenario give: 

Loan budget in ₹ crore (between 10 and 100). 

For Option A and Option B: interest rate %, processing fee %, expected default %, and cost of funds %. 

Rules: 

Use whole numbers or one decimal place only. 

Interest rate between 12% and 30%. 

Processing fee between 0% and 3%. 

Expected default between 1% and 12%. 

Cost of funds between 8% and 12%. 

In 3 scenarios, the option with the higher interest rate must make less profit because its expected default is much higher. 

In 1 scenario, both options must make exactly the same profit. 

Do not calculate profit and do not say which option is better. 

Output a table with these columns: ID | Budget | A Interest | A Fee | A Default | A Cost of Funds | B Interest | B Fee | B Default | B Cost of Funds. 

#### **<mark>2.3 AI-Generated Synthetic Dataset</mark>** 

|ID|Budget<br>(₹ cr)|A<br>Interest|A<br>Fee|A<br>Defaul<br>t|A<br>Cost|B<br>Interest|B Fee|B<br>Default|B Cost|
|---|---|---|---|---|---|---|---|---|---|
|S01|50|18|1|3|10|21|1.5|4|10|
|S02|60|26|2|11|10|19|1|2|9|
|S03|25|16|1|2|9|15|0.5|2.5|9|
|S04|80|22|2|6|10|19|1|2|10|
|S05|35|14|1|2|8|27|1|12|12|
|S06|90|29|2.5|11.5|11|23|1|4|10|
|S07|15|24|2|5|10|20|1|4|9|
|S08|70|17|1|3|9|20.5|1.5|4|10|



_All rates are in percentage._ 

#### **<mark>2.4 Dataset Verif</mark> i** **<mark>cation</mark>** 

After checking the dataset: 

- S02, S05 and S06 are trap scenarios. In each case, the option with a higher interest rate earns less profit. 

- S04 is the tie scenario because both options earn exactly the same profit. 

- All eight scenarios use fictional data. 

**Result:** The dataset contains the required three trap scenarios and one tie scenario. 

## **STEP 3: CALCULATE THE CORRECT ANSWERS YOURSELF** 

#### **<mark>3.1 Objective</mark>** 

Before testing AI, I calculated the correct net return and profit for all eight scenarios. This is important because an independent answer key helps us identify whether AI gives correct or incorrect results. 

I used the formulas given in Step 1 and calculated the results using a spreadsheet. 

#### **<mark>3.2 Calculation Method</mark>** 

Net Return = Interest Rate + Processing Fee − Expected Default − Cost of Funds 

Profit = Net Return ÷ 100 × Loan Budget 

#### **<mark>3.3 Answer Key</mark>** 

|**ID**|**A Net Return**|**A Profit (₹ cr)**|**B Net Return**|**B Profit (₹ cr)**|**Correct Choice**|
|---|---|---|---|---|---|
|S01|6%|3.00|8.5%|4.25|B|
|S02|7%|4.20|9%|5.40|B|
|S03|6%|1.50|4%|1.00|A|
|S04|8%|6.40|8%|6.40|B|
|S05|5%|1.75|4%|1.40|A|
|S06|9%|8.10|10%|9.00|B|
|S07|11%|1.65|8%|1.20|A|
|S08|6%|4.20|8%|5.60|B|



#### **<mark>3.4 Spreadsheet Formula</mark>** 

For example, if the interest rate, fee, default, cost of funds and budget are entered in separate spreadsheet cells, the formulas can be: 

###### **Net Return:** 

=Interest Rate + Processing Fee - Expected Default - Cost of Funds 

###### **Profit:** 

=Net Return/100*Loan Budget 

The same formulas are applied separately to Option A and Option B. 

**Result:** I calculated the answer key independently before testing the AI responses. This answer key will be used to check the accuracy of the AI in the next steps. 

## **STEP 4: TEST A SIMPLE DIRECT PROMPT** 

#### **<mark>4.1 Objective</mark>** 

The purpose of this step is to check whether AI can answer a simple question using direct prompting. 

In this task, AI only needs to compare the interest rates of Option A and Option B. No financial calculation is required. 

#### **<mark>4.2 Prompt Used</mark>** 

Here are 8 lending scenarios for KhataPe, a digital lender. 

For each scenario, which option has the higher interest rate? Answer only A or B. 

Output a table: ID | Higher Interest Rate 

Scenarios: 

[Paste the 8 scenarios from Step 2 here.] 

#### **<mark>4.3 ChatGPT Output</mark>** 

|**Scenario**|**Higher Interest Rate**|
|---|---|
|S01|B|
|S02|A|
|S03|A|
|S04|A|
|S05|B|
|S06|A|
|S07|A|
|S08|B|



#### **<mark>4.4 Observation</mark>** 

ChatGPT correctly identified the option with the higher interest rate in all eight scenarios. 

This task required only a simple comparison between two numbers. Therefore, direct prompting was sufficient and there was no need for detailed step-by-step calculations. 

###### **Result: 8 out of 8 correct.** 

## **STEP 5: TEST DIRECT PROMPTING FOR THE FINANCIAL DECISION** 

#### **<mark>5.1 Objective</mark>** 

In this step, I tested whether ChatGPT could select the more profitable loan option using a direct prompt. 

Unlike Step 4, this task requires multiple calculations, including net return, profit and the tie-breaking rule. 

#### **<mark>5.2 Prompt Used</mark>** 

You are a financial analyst at KhataPe, a digital lender. 

For each scenario below, decide which option KhataPe should choose to earn the higher profit. 

Rules: 

Net Return = Interest Rate + Processing Fee − Expected Default − Cost of Funds. 

Profit = Net Return × Loan Budget. 

If both profits are equal, choose the option with the lower expected default. 

Give the final answer only. Do not show any working. 

Output a table: ID | Choice (A or B) | Profit of Chosen Option (₹ crore). 

Scenarios: 

[Paste the same 8 scenarios here.] 

#### **<mark>5.3 ChatGPT Output</mark>** 

|**Scenario**|**Choice**|**Profit of Chosen Option (₹ crore)**|
|---|---|---|
|S01|B|4.25|
|S02|B|5.40|



|S03|A|1.50|
|---|---|---|
|S04|B|6.40|
|S05|A|1.75|
|S06|B|9.00|
|S07|A|1.65|
|S08|B|5.60|



#### **<mark>5.4 Comparison with the Answer Key</mark>** 

|**Scenario**|**Correct Choice**|**AI Choice**|**Result**|
|---|---|---|---|
|S01|B|B|Correct|
|S02|B|B|Correct|
|S03|A|A|Correct|
|S04|B|B|Correct|
|S05|A|A|Correct|
|S06|B|B|Correct|
|S07|A|A|Correct|
|S08|B|B|Correct|



#### **<mark>5.5 Observation</mark>** 

ChatGPT selected the correct option in all eight scenarios. It also correctly handled the tie scenario, S04, by selecting Option B because it had the lower expected default. 

However, the direct prompt provided only the final decision and profit figure. It did not show the calculations used to reach the answer. Therefore, it was difficult to verify the reasoning behind each decision. 

###### **Result: 8 out of 8 correct choices.** 

## **STEP 6: TEST STEP-BY-STEP PROMPTING** 

#### **<mark>6.1 Objective</mark>** 

The purpose of this step is to test whether asking AI to show its calculations makes the financial decision easier to understand and verify. 

The same eight scenarios and decision rules from Step 5 are used. The main difference is that AI is now asked to calculate net return and profit step by step. 

#### **<mark>6.2 Prompt Used</mark>** 

You are a financial analyst at KhataPe, a digital lender. 

For each scenario below, decide which option KhataPe should choose to earn the higher profit. 

Rules: 

Net Return = Interest Rate + Processing Fee − Expected Default − Cost of Funds. 

Profit = Net Return × Loan Budget. 

If both profits are equal, choose the option with the lower expected default. 

Think step by step. For each scenario: 

Step 1: Write the four numbers for Option A and calculate its net return. 

Step 2: Calculate Option A's profit in ₹ crore. 

Step 3: Repeat Steps 1 and 2 for Option B. 

Step 4: Compare the two profits and apply the tie rule if needed. 

Step 5: State the choice. 

Show your working for every scenario, then give a final summary table: ID | A Profit (₹ crore) | B Profit (₹ crore) | Choice. 

Scenarios: 

[Paste the same 8 scenarios here.] 

#### **<mark>6.3 ChatGPT Step-by-Step Output</mark>** 

**Scenario S01** 

###### **Option A:** 

Net Return = 18 + 1 − 3 − 10 = 6% 

Profit = 6 ÷ 100 × 50 = ₹3.00 crore 

**Option B:** 

Net Return = 21 + 1.5 − 4 − 10 = 8.5% 

Profit = 8.5 ÷ 100 × 50 = ₹4.25 crore 

**Decision:** Option B has higher profit. Choose Option B. 

**Scenario S02** 

###### **Option A:** 

Net Return = 26 + 2 − 11 − 10 = 7% 

Profit = 7 ÷ 100 × 60 = ₹4.20 crore 

###### **Option B:** 

Net Return = 19 + 1 − 2 − 9 = 9% 

Profit = 9 ÷ 100 × 60 = ₹5.40 crore 

**Decision:** Option B has higher profit. Choose Option B. 

**Scenario S03** 

**Option A:** 

Net Return = 16 + 1 − 2 − 9 = 6% 

Profit = 6 ÷ 100 × 25 = ₹1.50 crore 

###### **Option B:** 

Net Return = 15 + 0.5 − 2.5 − 9 = 4% 

Profit = 4 ÷ 100 × 25 = ₹1.00 crore 

**Decision:** Option A has higher profit. Choose Option A. 

**Scenario S04** 

###### **Option A:** 

Net Return = 22 + 2 − 6 − 10 = 8% 

Profit = 8 ÷ 100 × 80 = ₹6.40 crore 

**Option B:** 

Net Return = 19 + 1 − 2 − 10 = 8% 

Profit = 8 ÷ 100 × 80 = ₹6.40 crore 

Both options have equal profit. Option B has a lower expected default of 2%, compared with 6% for Option A. 

**Decision:** Choose Option B according to the tie-breaking rule. 

**Scenario S05** 

**Option A:** 

Net Return = 14 + 1 − 2 − 8 = 5% Profit = 5 ÷ 100 × 35 = ₹1.75 crore 

**Option B:** 

Net Return = 27 + 1 − 12 − 12 = 4% Profit = 4 ÷ 100 × 35 = ₹1.40 crore 

**Decision:** Option A has higher profits. Choose Option A. 

**Scenario S06** 

**Option A:** 

Net Return = 29 + 2.5 − 11.5 − 11 = 9% Profit = 9 ÷ 100 × 90 = ₹8.10 crore 

**Option B:** 

Net Return = 23 + 1 − 4 − 10 = 10% Profit = 10 ÷ 100 × 90 = ₹9.00 crore 

**Decision:** Option B has higher profit. Choose Option B. 

**Scenario S07** 

**Option A:** 

Net Return = 24 + 2 − 5 − 10 = 11% Profit = 11 ÷ 100 × 15 = ₹1.65 crore 

**Option B:** 

Net Return = 20 + 1 − 4 − 9 = 8% 

Profit = 8 ÷ 100 × 15 = ₹1.20 crore 

**Decision:** Option A has higher profit. Choose Option A. 

##### **Scenario S08** 

###### **Option A:** 

Net Return = 17 + 1 − 3 − 9 = 6% 

Profit = 6 ÷ 100 × 70 = ₹4.20 crore 

###### **Option B:** 

Net Return = 20.5 + 1.5 − 4 − 10 = 8% 

Profit = 8 ÷ 100 × 70 = ₹5.60 crore 

**Decision:** Option B has higher profit. Choose Option B. 

#### **<mark>6.4 Final Summary of Step-by-Step Results</mark>** 

|**Scenario**|**A Profit (₹ crore)**|**B Profit (₹ crore)**|**Final Choice**|
|---|---|---|---|
|S01|3.00|4.25|B|
|S02|4.20|5.40|B|
|S03|1.50|1.00|A|
|S04|6.40|6.40|B|
|S05|1.75|1.40|A|
|S06|8.10|9.00|B|
|S07|1.65|1.20|A|
|S08|4.20|5.60|B|



#### **<mark>6.5 Observation</mark>** 

ChatGPT correctly calculated the net return and profit for all eight scenarios. It also applied the tiebreaking rule correctly in S04. 

The main advantage of step-by-step prompting was that it showed the calculations for both options. This made it easier to check the figures and understand why a particular option was selected. 

###### **Result: 8 out of 8 correct choices.** 

## **STEP 7: VERIFY THE WORKING, CHANGE ONE NUMBER AND PREPARE A SCORECARD** 

#### **<mark>7.1 Part A: Verify the AI Working</mark>** 

I selected two trap scenarios, S02 and S05, to verify the calculations provided by ChatGPT. 

##### **Verification of S02** 

|**Calculation**|**AI Result**|**My Answer Key**|**Correct?**|
|---|---|---|---|
|Option A Net Return|7%|7%|Yes|
|Option A Profit|₹4.20 cr|₹4.20 cr|Yes|
|Option B Net Return|9%|9%|Yes|
|Option B Profit|₹5.40 cr|₹5.40 cr|Yes|
|Final Choice|B|B|Yes|



##### **Verification of S05** 

|**Calculation**|**AI Result**|**My Answer Key**|**Correct?**|
|---|---|---|---|
|Option A Net Return<br>i|5%|5%|Yes|
|Option A Profit|₹1.75 cr|₹1.75 cr|Yes|
|Option B Net Return|4%|4%|Yes|
|Option B Profit|₹1.40 cr|₹1.40 cr|Yes|
|Final Choice|A|A|Yes|



**<u>Observation:</u>** The calculations in both selected scenarios matched my independently prepared answer key. The verification confirmed that the AI used the correct formula and selected the correct option. 

#### **<mark>7.2 Part B: Change One Number</mark>** 

To check whether AI could update its calculations after a change in the data, I changed only one number in Scenario S01. 

The expected default rate of Option B was increased from 4% to 8%. All other numbers remained unchanged. 

##### **Prompt Used:** 

Change only one number: in S01, Option B's expected default is now 8%. Recalculate S01 step by step and tell me whether the choice changes. 

##### **ChatGPT Output** 

###### **Option A:** 

Net Return = 18 + 1 − 3 − 10 = 6% 

Profit = 6 ÷ 100 × 50 = ₹3.00 crore 

###### **Updated Option B:** 

Net Return = 21 + 1.5 − 8 − 10 = 4.5% 

Profit = 4.5 ÷ 100 × 50 = ₹2.25 crore 

###### **Final Decision:** 

Option A profit = ₹3.00 crore 

Option B profit = ₹2.25 crore 

Therefore, Option A now provides higher profit. 

**Result:** The decision changed from Option B to Option A after increasing Option B's expected default rate from 4% to 8%. 

This test showed that the AI updated its calculations and changed its final decision according to the new data. 

#### **<mark>7.3 Part C: Scorecard</mark>** 

The following scorecard compares the direct financial decision prompt from Step 5 with the step-by-step prompt from Step 6. 

|**Performance Measure**|**Direct Prompt (Step 5)**|**Step-by-Step Prompt (Step 6)**|
|---|---|---|
|Correct choices|8/8|8/8|
|Correct profit figures|8/8|8/8|
|Trap scenarios correct|3/3|3/3|
|Working available for checking|No|Yes|



#### **<mark>7.4 Ref</mark> l** **<mark>ection (Approximately 150 Words)</mark>** 

This lab helped me understand the difference between direct prompting and step-by-step prompting. Direct prompting worked well for simple questions, such as comparing two interest rates. It also gave the correct financial decisions in all eight scenarios in this test. However, it did not show the calculations, so checking the answers was difficult. 

Step-by-step prompting was more useful for understanding the financial decisions because it showed the net return and profit calculations for both options. It also made it easier to verify the trap scenarios and the tie scenario. The changed-number test showed that the AI could update its calculations when the expected default rate changed. 

However, AI should not be trusted without verification. The figures in this case do not include operating costs, taxes, collection costs or regulatory requirements. KhataPe should use AI as a decision-support tool, while a human analyst checks the calculations, lending risks and applicable rules before making the final decision. 

### **<u>Key Learnings</u>** 

1. Direct prompting is suitable for simple questions that require only one comparison. 

2. Step-by-step prompting makes financial calculations easier to understand and verify. 

3. A correct final answer does not always show how the AI reached its decision. 

4. Independent calculations are important for checking AI-generated results. 

5. AI can support financial decisions, but human verification is still necessary. 

### **<u>Recommendation to KhataPe</u>** 

KhataPe can use AI to support its monthly lending decisions. However, the company should prefer a process in which calculations are visible and independently checked. A human analyst should verify the figures, default risks, operating costs and regulatory requirements before approving a lending decision. 

### **<u>CONCLUSION</u>** 

This lab demonstrated how different prompting methods can be used to solve financial problems. 

Direct prompting was sufficient for simple comparisons and also produced correct financial decisions in the eight scenarios tested. However, step-by-step prompting provided more transparency by showing the calculations behind each decision. 

The experiment also showed the importance of preparing an independent answer key and verifying AIgenerated calculations. Even when AI provides a correct answer, a financial analyst should check the working before using it in a real business decision. 

Overall, AI can be a useful support tool for FinTech businesses, but it should not replace human judgement, financial verification, or regulatory checks. 

