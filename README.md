# Medical Claims Auditing Project

This project simulates the role of a healthcare data analyst tasked with vetting insurance claims. Using Medicare provider data, the analysis aims to uncover overbilling, unusual procedure use, regional cost differences, and provider-level anomalies through a mix of statistical checks, clustering, and custom rule-based auditing.

The first step involves detecting overbilling by comparing the average submitted charges to the Medicare-allowed amounts. Claims where providers billed more than three times the allowed amount were flagged for further review.

Next, the project checks for suspicious procedures by analyzing how often certain HCPCS codes appear within specific provider types. If a provider uses a procedure code that's uncommon for their type, that claim is flagged as potentially inconsistent or miscategorized.

The third part of the analysis compares costs between urban and rural providers. By grouping claims based on the provider’s location type, we examine whether geography influences submitted charges, which may point to systemic cost variation or irregular billing practices.

In the fourth step, the project applies the DBSCAN clustering algorithm to identify provider-level anomalies based on features like charges, allowed amounts, and number of services. This helps isolate providers whose billing behavior stands out from the rest.

Finally, a custom rule-based audit engine is used to combine various flags — such as extreme overcharging, high service counts with very few patients, and procedure-provider mismatches — into a single `Audit_Flags` column, which summarizes issues on a per-claim basis.

This project provides a practical demonstration of how data can be used to support claims vetting, cost control, and fraud detection in the health insurance domain.
