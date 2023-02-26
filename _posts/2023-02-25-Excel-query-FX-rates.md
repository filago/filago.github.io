---
title:  "Using Excel to Query Historical Currency Exchange Rates"
layout: post
categories:
  - Excel  
---

![Excel file screenshot](/assets/images/USD-GBP FX rate query, rev 5.png)

This took much more time to create than it could ever save me.  Fortunately, the point was to test & work on some Excel skills, not to save time.

A few key features of this workbook:
- pulls historical foreign exchange rates from a Federal Reserve Board website, into an Excel table.
- uses XLOOKUP formulas with spill to return records matching the user input dates, or closest earlier dates if not available. 
- uses further XLOOKUP formulas to provide the most recent valid rate when a rate is listed as ND (no data.)
