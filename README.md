# a-b_testing

**Objective**: Conduct an evaluation of the results of an A/B test.

**Tasks:**
- Data exploration and preprocessing.
- Evaluation of the dataset's correctness:
  - Compliance with the requirements of the technical specification.
  - Test duration.
  - Test audience.
- Exploratory data analysis:
  - Check if the number of events per user is evenly distributed across the samples.
  - Analyze the distribution of events per day.
  - Examine the conversion rate in the funnel across different stages.
  - Identify any data peculiarities to consider before starting A/B testing.
- Evaluation of A/B test results.
- Conclusions.

**Data Description**

The available dataset includes user actions, a technical specification, and several auxiliary datasets.

`ab_project_marketing_events.csv` — marketing event calendar for the year 2020.

File structure:
- `name` — name of the marketing event.
- `regions` — regions where the advertising campaign will be conducted.
- `start_dt` — start date of the campaign.
- `finish_dt` — end date of the campaign.

`final_ab_new_users.csv` — users who registered from December 7th to December 21st, 2020.

File structure:
- `user_id` — user identifier.
- `first_date` — registration date.
- `region` — user region.
- `device` — device used for registration.

`final_ab_events.csv` — actions of new users from December 7th, 2020, to January 4th, 2021.

File structure:
- `user_id` — user identifier.
- `event_dt` — event date and time.
- `event_name` — type of event.
- `details` — additional event data. For example, for purchases, the purchase cost in dollars is stored in this field.

`final_ab_participants.csv` — table of test participants.

File structure:
- `user_id` — user identifier.
- `ab_test` — test name.
- `group` — user group.

**Technical Specification**

- Test name: `recommender_system_test`.
- Groups: A (control), B (new payment funnel).
- Launch date: 2020-12-07.
- New user enrollment stop date: 2020-12-21.
- End date: 2021-01-04.
- Target audience: 15% of new users from the EU region should be selected for the test.
- Test purpose: test the changes associated with the implementation of an improved recommendation system.
- Expected number of test participants: 6000.
- Expected effect: within 14 days from registration, users will show an improvement in each metric by at least 10%:
  - Conversion rate to product page views (event: `product_page`).
  - Views of the product cart (event: `product_cart`).
  - Purchases (event: `purchase`).
