---
title:  "Using Excel to Query Historical Currency Exchange Rates"
layout: post
categories:
  - Excel  
---

![Excel file screenshot](/assets/images/USD-GBP FX rate query, rev 4.png)

This took way more time to create than it could possibly ever save me.  The real value to me is what I learned along the way.

A few key features of this workbook:
- pulls historical foreign exchange rates from a Federal Reserve Board website, into an Excel table.
- uses XLOOKUP formulas with spill to return records matching the user input dates, or closest earlier dates if not available. 
- uses further XLOOKUP formulas to provide the most recent valid rate when a rate is listed as ND (no data.)
