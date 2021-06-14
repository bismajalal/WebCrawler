# WebCrawler

This notebook is a Web Crawler which takes a few links and crawls the websites those link redirect to. 

There is a URL frontier class which has front queues to maintain priority and back queues to maintain politeness. 
When a backqueue is empty a link is added to it from a frontqueue. A backqueue only has the link for a particular domain.
After retrieving a link from the backqueue, its content is extract from the webserver using BeautifulSouop library.
All of the URLs in that page are retrieved and converted to absolute URLS if they are relative URLs.
Before crawling any website, its robot.txt file is accessed to see if crawling is allowed for that website.
The new URLs that are extracted are checked against that ones that are already in the frontier.
If a new URL is same as a URL already in the frontier or if it is same as the one which has already been crawler, the new URL is discared.
The process stops are 1000 URLs are crawled.
