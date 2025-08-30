# 📸 Instagram Database Simulation Project 🎉

Welcome to the **Instagram Database Simulation Project!** This project takes you behind the scenes of how a simplified Instagram database works. From managing users and their posts to tracking likes, comments, follows, and even photo tags, this database has it all. It's like creating your own mini-Instagram, minus the addictive scrolling! 🚀

---

## ✨ Features

This database can do the following:

* **User Management**: Keep track of all users with unique IDs, names, and profile information. 👥
* **Photo Collection**: Store all the snapshots, captions, and timestamps of when they were uploaded. 📷
* **Followers & Following**: Manage who’s following who. 🫣
* **Likes**: Track who’s double-tapping on which photo. ❤️
* **Comments**: Save all the witty, supportive, or random comments users leave on photos. 🗨️
* **Tags**: Users tagging their friends or influencers tagging brands? All in the database! 🏷️
* **Photo Tags**: Identify which photos are tagged with specific keywords like #ThrowbackThursday or #NoFilter. 🔖

---

## 🔧 How It Works

This project uses a **relational database model** to organize Instagram-like data efficiently.

### Tables

* **Users**: user\_id, name, bio
* **Photos**: photo\_id, user\_id, upload\_date, caption
* **Follows**: follower\_id, followee\_id
* **Likes**: user\_id, photo\_id
* **Comments**: comment\_id, photo\_id, user\_id, comment\_text
* **Tags**: tag\_id, tag\_name
* **Photo\_Tags**: photo\_id, tag\_id

### Tasks Performed

* 🚀 **Who’s Insta Famous?** → Find the user with the most followers
* ❤️ **Most Loved Photo** → Identify which photo got the most likes
* 🗨️ **Comment King/Queen** → Find the most active commenter
* 🏷️ **Hashtag Hunt** → Find photos with specific tags (e.g., #TravelGoals)
* 🔄 **Mutual Friends** → Determine mutual followers between users

---

## 🛠️ Tools Used

* **Database**: MySQL / PostgreSQL
* **Query Language**: SQL
* **Scripting**: Python (optional) for automation
* **Visualization**: Matplotlib, Seaborn

---

## 🎯 How to Run the Project

1. **Set up the database**:

   * Import the provided schema (`instagram_schema.sql`).
   * Populate the tables using the sample dataset or your own data.

2. **Perform queries**:

   * Use the provided SQL queries to analyze data.
   * Modify queries to explore more insights.

3. **Visualize results**:

   * Export query results.
   * Create charts or tables using Python visualization libraries.

---

## 🌟 Example Queries

**Top 5 Most Followed Users:**

```sql
SELECT user_id, COUNT(follower_id) AS follower_count
FROM Follows
GROUP BY user_id
ORDER BY follower_count DESC
LIMIT 5;
```

**Most Popular Photo:**

```sql
SELECT photo_id, COUNT(user_id) AS like_count
FROM Likes
GROUP BY photo_id
ORDER BY like_count DESC
LIMIT 1;
```

**Photos Tagged with #Travel:**

```sql
SELECT Photos.photo_id, Photos.caption
FROM Photo_Tags
JOIN Tags ON Photo_Tags.tag_id = Tags.tag_id
JOIN Photos ON Photo_Tags.photo_id = Photos.photo_id
WHERE Tags.tag_name = '#Travel';
```

---

## 💡 Fun Ideas

* Create a **leaderboard** for users based on likes and comments.
* Simulate new users joining and interacting.
* Add more features like **Stories** or **Highlights**.

---

## 📚 Learning Outcomes

By working on this project, you’ll gain experience with:

* Designing and implementing relational databases
* Writing SQL queries for analysis
* Simulating social media database structures
* Analyzing and visualizing data for insights

---

## 🥳 Closing Thoughts

This project is not just about SQL—it’s about exploring how popular platforms like Instagram work under the hood. So, dive in, have fun, and flex those **data management skills!** 💪

Feel free to share feedback or suggestions for improvements. Let’s make this Insta database even cooler! 🚀

---

<p align="center"><b>Made WITH   ❤️ by Prapti Mishra</b></p>
<p align="center"><i>Pull Requests Allowed ✅</i></p>
