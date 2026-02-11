# Automated Underwriting Rules Engine

## Business Context

In commercial insurance, underwriters evaluate thousands of applications to decide whether to accept risk, refer for manual review, or decline. This decision-making process balances **risk appetite** (what risks the insurer is willing to take) against **growth objectives** (writing profitable business).

An automated underwriting rules engine streamlines this process by:
- **Straight-through processing** low-risk applications that meet clear acceptance criteria
- **Referring** complex or borderline cases to experienced underwriters
- **Declining** applications outside risk appetite automatically

This project simulates a commercial insurance underwriting decision engine for small-to-medium enterprises (SMEs), focusing on general liability and property coverage.

## Why This Matters for Underwriting

**For Insurers:**
- Improves efficiency: 40-60% of applications can be straight-through processed
- Ensures consistency: Rules encode risk appetite uniformly across the portfolio
- Frees underwriter time: Focus on complex risks requiring judgment
- Portfolio management: Controls exposure concentration and accumulation

**For This Project:**
- Demonstrates understanding of underwriting workflow beyond just data analysis
- Shows ability to translate business strategy (risk appetite) into operational rules
- Bridges data/analytics skills with insurance domain knowledge
- Relevant to InsurTech and data-driven underwriting roles

## Key Underwriting Concepts

### Risk Appetite
The types and levels of risk an insurer is willing to accept, defined by:
- **Industry sectors**: Which business types to target/avoid
- **Size limits**: Maximum revenue/exposure per policy
- **Geographic restrictions**: Areas with catastrophe exposure or regulatory concerns
- **Loss history**: Maximum acceptable prior claims
- **Coverage limits**: Maximum liability the insurer will offer

### Decision Outcomes
- **ACCEPT**: Application meets all acceptance criteria → issue quote automatically
- **REFER**: Falls outside auto-accept parameters but within overall appetite → manual review
- **DECLINE**: Outside risk appetite or prohibited risk → automatic rejection

### Key Metrics
- **Straight-through rate**: % of applications auto-accepted (target: 40-50%)
- **Referral rate**: % requiring manual review (target: 30-40%)
- **Decline rate**: % outside appetite (target: 10-20%)

## Project Structure

```
underwriting-rules-engine/
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
├── data/
│   ├── applications.csv              # Sample insurance applications
│   └── data_dictionary.md            # Field definitions
├── src/
│   ├── data_generator.py             # Generate synthetic applications
│   ├── risk_rules.py                 # Core underwriting rules
│   ├── decision_engine.py            # Main decision logic
│   └── dashboard.py                  # Visualization and analysis
├── notebooks/
│   └── exploratory_analysis.ipynb    # EDA and testing
├── docs/
│   ├── risk_appetite.md              # Risk appetite documentation
│   └── implementation_guide.md       # Step-by-step build guide
└── tests/
    └── test_rules.py                 # Unit tests for rules

```

## Features

### 1. Risk Assessment Rules
- Industry classification and risk scoring
- Revenue-based exposure limits
- Geographic risk evaluation
- Claims history assessment
- Coverage adequacy checks

### 2. Decision Engine
- Multi-factor rule evaluation
- Priority-based rule processing
- Clear audit trail for each decision
- Configurable risk appetite parameters

### 3. Analytics Dashboard
- Decision distribution (accept/refer/decline)
- Referral reason analysis
- Industry and geographic concentration
- Risk score distribution
- Acceptance rate trends

## Sample Decision Flow

```
Application: Coffee Shop, £500K revenue, London, 0 claims
│
├─ Industry Check: ✓ Approved (Food & Beverage)
├─ Revenue Check: ✓ Within limits (< £1M auto-accept threshold)
├─ Location Check: ✓ Approved territory
├─ Claims Check: ✓ Clean history
└─ Coverage Check: ✓ Appropriate limits
    │
    └─ DECISION: ACCEPT
```

```
Application: Cryptocurrency Exchange, £10M revenue, London, 1 claim
│
├─ Industry Check: ⚠ Emerging risk (refer for specialist assessment)
├─ Revenue Check: ⚠ Exceeds authority limit (£5M threshold)
└─ Claims Check: ✓ Acceptable history
    │
    └─ DECISION: REFER
       Reasons: 
       - Industry requires specialist underwriting
       - Revenue exceeds automated authority limit
```

## Key Insights from Analysis

*(To be completed after building)*

- **Straight-through rate**: XX% of applications auto-accepted
- **Top referral reasons**: Industry complexity, revenue limits, geographic concentration
- **Decline patterns**: Adverse claims history, prohibited industries
- **Portfolio composition**: Industry and geographic distribution of accepted risks

## Technical Approach

### Data Generation
- Realistic synthetic application data spanning multiple industries
- Controlled distribution of risk factors (revenue, claims, location)
- Includes edge cases to test rule logic

### Rules Engine
- Modular rule design for maintainability
- Configurable thresholds and parameters
- Clear separation of rules from decision logic
- Comprehensive logging for audit trail

### Visualization
- Power BI for interactive dashboard
- Python (Matplotlib/Plotly) for embedded charts
- Clear presentation of underwriting metrics

## Business Applications

This rules engine approach is used by:
- **Traditional insurers**: Zurich, AIG, AXA for SME underwriting
- **InsurTech companies**: CFC, Corvus, Coalition for automated binding
- **MGAs**: Delegated authority underwriting with rules governance
- **Reinsurance**: Treaty acceptance decisions

## Future Enhancements

1. **Machine learning integration**: Predictive loss scoring to augment rules
2. **Dynamic pricing**: Link decisions to premium calculation
3. **Portfolio monitoring**: Real-time exposure accumulation tracking
4. **API integration**: Connect to rating engines and policy admin systems
5. **A/B testing framework**: Test rule changes impact on portfolio quality

## Getting Started

See [Implementation Guide](docs/implementation_guide.md) for step-by-step instructions.

## Author

**Ben Shinnick**
- Economics & Management graduate transitioning to data analytics
- Building practical insurance industry knowledge
- Interested in commercial underwriting and InsurTech
- [LinkedIn](https://linkedin.com/in/ben-shinnick-674969252/) | [GitHub](https://github.com/bpshinnick1)

## Acknowledgments

This project simulates commercial insurance underwriting principles. Risk appetite parameters and rules are illustrative and simplified for educational purposes.

---

**License**: MIT  
**Last Updated**: February 2026
