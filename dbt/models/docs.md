{% docs hcp_id %}
Unique identifier for a healthcare professional in our system. This identifier is consistently used across all data sources and models.
{% enddocs %}

{% docs hcp_specialty %}
Medical specialty or practice area of the healthcare professional. Common values include Cardiology, Neurology, Oncology, Primary Care, and Psychiatry.
{% enddocs %}

{% docs territory_id %}
Unique identifier for a sales territory. Territories are geographical areas assigned to sales representatives for customer engagement and sales activities.
{% enddocs %}

{% docs visit_type %}
Type of interaction between a medical representative and a healthcare professional. Can be one of: In-person, Virtual, or Phone call.
{% enddocs %}

{% docs engagement_score %}
A numerical score from 0-10 that represents the level of engagement during an interaction. Higher scores indicate more positive and productive interactions.
- 0-3: Low engagement
- 4-6: Medium engagement
- 7-10: High engagement
{% enddocs %}

{% docs product %}
Name of a pharmaceutical product in our portfolio. All product names are standardized across the database.
{% enddocs %}

{% docs estimated_revenue %}
Calculated revenue derived from prescription data. Computed as the product of total prescribed units and the price per unit of the product.
{% enddocs %}

{% docs potential_category %}
Classification of an HCP based on their potential value:
- High: potential_score >= 70
- Medium: potential_score >= 30 and < 70
- Low: potential_score < 30
{% enddocs %}

{% docs hcp_segment %}
Strategic segmentation of healthcare professionals based on their potential value and influence:
- Key Target: High potential and high influence HCPs
- Priority: High potential or high influence HCPs
- Standard: Medium or low potential and influence HCPs
{% enddocs %} 