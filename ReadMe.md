## BUSINESS CASE
The '27 Club' is a romantic idea that live fast die young musicians tend to die at 27. The idea first surfaced after Jimi Hendrix, Janis Joplin and Jim Morrison tragically passed away within the span of two years of each other and all at the age of 27.

A study in the [Conversation](http://theconversation.com/the-27-club-is-a-myth-56-is-the-bum-note-for-musicians-33586) showed that in a population of dead musicians spanning 1950 to 2010 (n = 11054) had a bi-modal age distribution with the first mode being 56 years old. 1.3% of the population died at the age of 27, this would need to have been 1.6% to be considered a significant proportion of the population.

The authors do not compare the distribution to a 'global' distribution. Although a 'life of excess' would lead to tragic early deaths - it would also lead to later, but still early deaths related to chronic substance abuse.

The question I have is: **do musicians tend to die earlier than a global average?**

This question could be explored further by looking at different factors such as: success, region and genre.

## DATASET
**Musician Death Data** - Use Wikipedia API to return a list of page members of category Musician. Web scrape from Wikipedia the age of birth and death. Calculate the death age. Plot a histogram of death ages.

**Global Death Data**
	* Use a single mean value
    * Use a single global mean or a mean of mean from all countries
        * (central-only) WHO publishes the annual life expectancy for each country and several regional aggregations.
       
       
## ANALYSES

* One-Tail Hypothesis Test: "Musicians do not die, on average, at an earlier age than the global mean?"

## IMPACT
Interesting trivia. Tutorial on how to use Wikipedia API and how to web scrape Wikipedia. An interesting dataset.

## Workflows

* **ReplicateFigure**: List_Catmembers | Dict_AgeAtDeath | AgeAtDeath_ReplicateFigure
* One Sample Hypthesis Test

### Sub Work Flows

* **List_Catmembers**: Return a list of musicians from wikipedia
* **Dict_AgeAtDeath**: Returns a dictionary of musicians and age at death
* **AgeAtDeath_Replicate**: List_Catmembers | DictAgeAtDeath, replicate figure
    
## Functions

* **return_cat_pages**: given list of categories, return all pages
    * **format_wiki_cat**: adds 'Category:' prior to category name
    * **catmembers_list**: given category, return all pages 
	
* **death_age**: given list of wiki page names, return dictionary = ['Person Name']: Age At Death
    * **person_born_dead**: given page name, return set of (Born date, Death date)
    * **create_wiki_url**: given page name, return wikipedia url
    * **scrape_wiki_page**: given wikipedia url, return scraped text
    * **calculate_age**: given birth & death, return age at death
    
* SaveLoad: use JSON to dump and load dictionaries
        
## Tests

* Dictionary conditional values: filter a dictionary
* Dictoinary structure: find number of items in dictionary, sample randomly
* return_cat_pages()

## Successes

* Given list of people, return date of birth and death from wikipedia page
* Give list of categories, return list of category members as wikipedia page names
* Given list of people, return dictionary with name: age at death
* Given age at death dictionary, create a histogram of counts or percents by age
* Storing dictionaries locally

## Next Steps

* Comparison to Conversation results
* Write Up
