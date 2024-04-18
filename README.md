# Webscraping
library(robotstxt)
library(rvest)
link = "https://technologymagazine.com/articles/apple-bringing-spatial-computing-to-business-with-vision-pro"
path = paths_allowed(link)
web = read_html(link)
View(web)
tech = web  %>% html_node("p:nth-child(9) , #onetrust-accept-btn-handler , .WidgetWrapper_WidgetWrapper__R4uge+ .WidgetWrapper_WidgetWrapper__R4uge p:nth-child(3)") %>% html_text()
View(tech)
t = data.frame(tech)
View(t)
write.dcf(t,"latest technology.doc")
