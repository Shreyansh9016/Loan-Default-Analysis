<h1 align="center">📊 End-to-End Loan Default Analysis</h1>
<h3 align="center">Excel → SQL Server → Power BI Dataflow → Power BI Dashboards</h3>

<hr/>

<h2>📌 Project Overview</h2>
<p>
This project demonstrates a complete <b>end-to-end Business Intelligence (BI) pipeline</b> for analyzing
<b>loan default behavior</b>. The workflow starts with raw Excel data ingestion into
<b>SQL Server Management Studio (SSMS)</b>, followed by data cleaning and transformation, and finally
interactive reporting in <b>Power BI</b> using <b>Power BI Dataflows</b> to support
<b>automatic scheduled refresh and near real-time analysis</b>.
</p>

<p>
The analysis focuses on understanding how <b>borrower demographics, financial attributes,
credit risk indicators, and loan characteristics</b> influence default behavior.
</p>

<hr/>

<h2>🏗️ Architecture & Data Flow</h2>

<pre>
Excel Dataset
     ↓
SQL Server Management Studio (Data Cleaning & Transformation)
     ↓
Power BI Dataflow (Centralized, Auto-Refreshed Data Layer)
     ↓
Power BI Desktop (DAX Measures & Data Modeling)
     ↓
Dashboards & PDF Report
</pre>

<hr/>

<h2>🗂️ Repository Structure</h2>

<pre>
├── Loan_Default.xlsx                # Raw loan dataset
├── Column_Definition.xlsx           # Column descriptions & metadata
├── E2E1.pbix                        # Power BI report file
├── Report.pdf                       # Exported Power BI report
├── Dashboard/                       # Dashboard screenshots
└── README.md                        # Project documentation
</pre>

<hr/>

<h2>📄 Dataset Description</h2>
<p>
The <b>Loan_default</b> table contains detailed information about loan applicants,
their financial profile, loan attributes, and repayment behavior.
</p>

<h3>📌 Key Dataset Columns</h3>
<ul>
  <li><b>LoanID</b> – Unique identifier for each loan</li>
  <li><b>Age</b>, <b>Age Group</b> – Applicant age and categorized age bands</li>
  <li><b>EmploymentType</b> – Employment category of the borrower</li>
  <li><b>Education</b> – Education qualification of the applicant</li>
  <li><b>MaritalStatus</b> – Marital status of the borrower</li>
  <li><b>Income</b>, <b>Income Bracket</b> – Applicant income and grouped income range</li>
  <li><b>CreditScore</b>, <b>Credit Score Bins</b> – Credit score and risk segmentation</li>
  <li><b>DTIRatio</b> – Debt-to-Income ratio</li>
  <li><b>InterestRate</b> – Loan interest rate</li>
  <li><b>LoanAmount</b> – Approved loan amount</li>
  <li><b>LoanPurpose</b> – Purpose of the loan</li>
  <li><b>LoanTerm</b> – Duration of the loan</li>
  <li><b>MonthsEmployed</b> – Employment tenure</li>
  <li><b>NumCreditLines</b> – Number of active credit lines</li>
  <li><b>HasCoSigner</b>, <b>HasDependents</b>, <b>HasMortgage</b> – Financial obligations</li>
  <li><b>Loan_Date_DD_MM_YYYY</b> – Loan application date</li>
  <li><b>Year</b> – Derived year field for trend analysis</li>
  <li><b>Default</b> – Loan default indicator</li>
</ul>

<p>
A separate <b>Column Definition file</b> is included to ensure clarity and business understanding of each field.
</p>

<hr/>

<h2>🧹 Data Cleaning & Preparation (SQL Server)</h2>
<ul>
  <li>Imported Excel data into <b>SQL Server Management Studio</b></li>
  <li>Handled missing and blank values</li>
  <li>Standardized categorical fields</li>
  <li>Created derived columns such as <b>Age Group, Credit Score Bins, Income Brackets, and Year</b></li>
  <li>Validated cleaned data before publishing to Power BI</li>
</ul>

<hr/>

<h2>🔄 Why Power BI Dataflow Is Used</h2>
<p>
<b>Power BI Dataflows</b> are used as a centralized data preparation and storage layer between SQL Server
and Power BI reports.
</p>

<h4>Benefits of Using Dataflows:</h4>
<ul>
  <li><b>Centralized Transformations</b> – Data cleaning logic is written once and reused</li>
  <li><b>Scheduled Auto Refresh</b> – Dashboards update automatically at defined intervals</li>
  <li><b>Near Real-Time Analytics</b> – Reflects updated SQL data without manual refresh</li>
  <li><b>Scalability</b> – Same dataflow can serve multiple Power BI reports</li>
  <li><b>Enterprise BI Architecture</b> – Separation of data engineering and reporting layers</li>
</ul>

<hr/>

<h2>📈 Power BI Dashboards</h2>

<h3>🔹 Loan Default – Overview</h3>
<img width="1294" height="723" alt="image" src="https://github.com/user-attachments/assets/c3becbc9-811b-4ec1-9662-891d4a35f800" />

<h3>🔹 Applicant Demographics & Financial Profile</h3>
<img width="1286" height="728" alt="image" src="https://github.com/user-attachments/assets/705379cd-2809-48c0-8158-5106b7eb0a51" />

<h3>🔹 Financial Risk Metrics</h3>
<img width="1288" height="729" alt="image" src="https://github.com/user-attachments/assets/2a5d690a-dcba-4b02-8982-ec3f6a16c77e" />

<hr/>

<h2>🧮 DAX Measures & Measure Tables</h2>

<h3>Measures Table 1</h3>
<ul>
  <li>Loan Amount by Purpose</li>
  <li>Average Income by Employment Type</li>
  <li>Average Loan Amount by Age Group</li>
  <li>Default Rate by Employment Type</li>
  <li>Default Rate by Year</li>
</ul>

<h3>Measures Table 2</h3>
<ul>
  <li>Average Loan Amount (High Credit)</li>
  <li>Loan by Education Type</li>
  <li>Median Loan Amount by Credit Score Bins</li>
  <li>Total Loan Amount by Credit Bins</li>
  <li>Total Loan Amount (Middle Age Adults)</li>
</ul>

<h3>Measures Table 3</h3>
<ul>
  <li>Year-over-Year (YoY) Loan Amount Change</li>
  <li>Year-over-Year (YoY) Default Loan Change</li>
  <li>Year-to-Date (YTD) Loan Amount</li>
</ul>

<p>
Advanced DAX functions such as <b>CALCULATE, FILTER, ALLEXCEPT, SUMX, AVERAGEX,
MEDIANX, VALUES, and DATESYTD</b> are used extensively to control filter context
and deliver accurate insights.
</p>

<hr/>

<h2>📊 Key Insights Delivered</h2>
<ul>
  <li>Identification of high-risk credit and employment segments</li>
  <li>Loan distribution trends across age groups and purposes</li>
  <li>Default rate comparison by year and employment type</li>
  <li>Impact of credit score on loan size and default probability</li>
  <li>YoY and YTD performance tracking</li>
</ul>

<hr/>

<h2>🛠️ Tools & Technologies</h2>
<ul>
  <li><b>Excel</b> – Raw data source</li>
  <li><b>SQL Server (SSMS)</b> – Data storage and transformation</li>
  <li><b>Power BI Dataflows</b> – Centralized, auto-refreshed data layer</li>
  <li><b>Power BI Desktop</b> – Data modeling, DAX, visualization</li>
  <li><b>DAX</b> – Analytical calculations</li>
</ul>

<hr/>

<h2>🚀 Project Highlights</h2>
<ul>
  <li>True <b>end-to-end BI pipeline</b></li>
  <li>Enterprise-style <b>Dataflow architecture</b></li>
  <li>Well-organized <b>measure tables</b></li>
  <li>Portfolio-ready financial analytics project</li>
</ul>

<hr/>

<h2>👤 Author</h2>
<p>
<b>Shreyansh Singh</b><br/>
Data Analyst<br/>
<a href="https://www.linkedin.com/in/shreyansh-singh-729b0b198/">LinkedIn</a> |
<a href="https://github.com/Shreyansh9016">GitHub</a>
</p>
