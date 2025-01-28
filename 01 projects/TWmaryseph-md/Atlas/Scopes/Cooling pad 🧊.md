up:: [[00 Home 🏠 - v4]]
tags:: #atlas/Scope 

# Cooling pad 🧊

Using `date:` inline metadata, this datascope looks at the 20 newest notes in your **• Inbox** folder over 7 days old.

As you process each note, move them to the best folder, make connections, add details, and delete everything that no longer *sparks* ✨. 

---


```dataview
TABLE without id
file.link as "Encounters and new ideas", (date(today) - file.day).day AS "Days Alive"
FROM "+ Inbox"
WHERE (date(today) - file.day).day > 1
SORT file.day ASC
LIMIT 20
```