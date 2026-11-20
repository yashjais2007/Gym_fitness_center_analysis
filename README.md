# Gym_fitness_center_analysis
#task 15: write five facility management and retention recommendations
peak_hour = df["Hour"].value_counts().idxmax()
busiest_day = df["Weekday"].value_counts().idxmax()

top_class = df[df["Fitness_Class"] != "None"]["Fitness_Class"].value_counts().idxmax()
solo_visits_pct = (df["Fitness_Class"] == "None").mean() * 100

top_tier = df["Membership_Tier"].value_counts().idxmax()
low_eng_count = len(unique_low_engagement_members)

recommendations = [
    f"1. Optimize Peak-Hour Staffing: {busiest_day}s and {peak_hour}:00 see the highest check-in volume. Schedule extra floor trainers and pre-peak equipment checks ahead of this window to reduce wait times.",
    f"2. Expand Top-Performing Class Capacity: '{top_class}' is the highest-attended fitness class. Add extra {top_class} sessions during peak evening and morning slots on {busiest_day}s to capture unmet demand.",
    f"3. Convert Solo Gym-Goers to Group Classes: {solo_visits_pct:.1f}% of check-ins do not include a fitness class ('None'). Offer a complimentary trial class pass to solo visitors to boost routine consistency and retention.",
    f"4. Launch Automated Low-Engagement Outreach: {low_eng_count} members logged fewer than 2 visits in a month. Trigger automated check-in reminders and offer a free 1-on-1 trainer consultation to re-engage at-risk members.",
    f"5. Align Tier Pricing & Upgrade Pathways: '{top_tier}' generates the highest visit volume, while monthly fees (₹999, ₹1,499, ₹2,499) overlap across tiers. Standardize tier pricing and offer high-frequency ₹999/₹1,499 members a discounted 30-day Platinum upgrade trial."
]

print("--- Facility Management & Retention Recommendations ---")
for rec in recommendations:
    print(rec)
