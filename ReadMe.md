## BUSINESS CASE
The '27 Club' is a romantic idea that exceptionally talented musicians tend to die at the age of 27. The idea was first coined after Jimi Hendrix, Janis Joplin and Jim Morrison tragically passed away within the span of two years of each other and all at the age of 27. Recently, the deaths of Kurt Cobain and Amy Winehouse have sparked interest in this notion as well.

A study in the [Conversation](http://theconversation.com/the-27-club-is-a-myth-56-is-the-bum-note-for-musicians-33586) showed that in a population of dead musicians spanning 1950 to 2010 (n = 11054) had a bi-modal age distribution with the first mode being 56 years old. 1.3% of the population died at the age of 27, this would need to have been 1.6% to be considered a significant proportion of the population.

The authors do not discuss the shape of the distribution (bi-modal) and also do not compare the distribution to a 'global' distribution. Although a 'life of excess' would lead to tragic early deaths - it would also lead to later, but still early deaths related to chronic substance abuse.

The question I have is: **do musicians tend to die earlier than a global average?**

This question could be explored further by looking at different factors such as: success, region and genre.

## DATASET
**Musician Death Data** - Using the Wikipedia API I would gather information about musicians and their age of death. At the same time it would be interesting to see if other information could be extracted.

**Global Death Data**
	* WHO publishes the annual life expectancy for each country and several regional aggregations. The issue is that only the central estimate is included without any information about variation.
	* When scraping Wikipedia for the death ages of musicians I could also do a more global grab and use that as the total population.

## IMPACT
There is a general curiosity about this group, as it is a very romantic idea. This means that it could result in traffic and general interest showcasing my skillset. The project itself would showcase my ability to build a pipeline to visualize open sourced data. I also have the opportunity to publish this in the **Conversation** as a follow on from the previous study.

## Workflows
    * **Histogram_AgeAtDeath**: Creates a histogram of age at death
    
## Functions
    * **return_cat_pages**: given list of categories, return all pages
        * **format_wiki_cat**: adds 'Category:' prior to category name
        * **catmembers_list**: given category, return all pages 
	
	* **death_age**: given list of wiki page names, return dictionary = ['Person Name']: Age At Death
        * **person_born_dead**: given page name, return set of (Born date, Death date)
        * **create_wiki_url**: given page name, return wikipedia url
        * **scrape_wiki_page**: given wikipedia url, return scraped text
        * **calculate_age**: given birth & death, return age at death

## Successes
    * Given list of people, return date of birth and death from wikipedia page
    * Give list of categories, return list of category members as wikipedia page names

## Next Steps
    * Feed results of **return_cat_pages** into **return_people_dates**
    * * Error - negative ages; also 16 hours to return results
	* Return age at death
	* Construct histogram of age at death
