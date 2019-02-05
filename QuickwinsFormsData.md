# Quick Win - Submitting data through Logic Apps from the web
**Produced by Dave Lusty**

# Introduction
This demo shows how you can use a simple HTML form stored in Blob storage to submit data and store it as JSON (or any other format) in Logic Apps. This is useful for when you need to collect a tiny piece of data that you don't currenlty have in a database. A great alternative would also be PowerApps, but this method is simple and many people already know HTML and possibly Javascript so this concept will be handy for your toolkit.

# Website
For this demo we need a very simple website. When i say simple I mean a single HTML page with a single form on it. This will be used to submit our data which the Logic App will store to Blob Storage, or we could just as easily insert into Azure SQL DB or Cosmos DB with the same technique.
## HTML Content


'''HTML
<!DOCTYPE html>
<html>
<head>
	<title>Test Form</title>
</head>
<body>
<form action="https://prod-20.centralus.logic.azure.com:443/workflows/d22a2b332b9d46a989060c468a10254f/triggers/manual/paths/invoke?api-version=2016-10-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=JU7G7dqodkhyS7KvYXn8kxuYANJnctqKYmleLNLywy8"  method="post">
  First name:<br>
  <input type="text" name="firstname"><br>
	Last name:<br>
  <input type="text" name="lastname"><br>
	Date:
  <input type="date" name="date">
	<input type="submit" value="Submit">
</form>
</body>
</html>
'''