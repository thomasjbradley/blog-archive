# Open Data Ottawa

**My trials and tribulations in creating the Ottawa Park data set and a little overview of what my Open Data Ottawa app will be.**

Open Data is an important step for current governments and there has been a lot of discussion around the blog sphere. I won’t cover material that has already been documented elsewhere, but I do want to mention a local initiative, [Open Data Ottawa](http://opendataottawa.ca).

The City of Ottawa is very close to declaring the itself ‘open’ and to encourage the city departments to start opening up the data the Open Data Ottawa Hackfest was arranged.

It is **Saturday, April 24th, 2010** and [tickets to the event are free, go reserve them](http://guestlistapp.com/events/20361).

## A Few Open Data Ottawa Links

- [Open Data Ottawa](http://opendataottawa.ca/)
- [Open Data Ottawa Blog](http://blog.opendataottawa.ca/)
- [Open Data Ottawa App List](http://apps.opendataottawa.ca/)
- [Open Data Ottawa Registration](http://guestlistapp.com/events/20361)
- [Open Data Ottawa on Twitter](http://twitter.com/opendataottawa)

## Ottawa Parks Data Set

For my contribution to the Open Data Ottawa Hackfest I am creating an application (more on that in a second) but first I needed a data set.

The city’s web site has a [list of all the parks](http://ottawa.ca/rec_culture/park_facility/parks/locations/index_en.html) in Ottawa and their addresses. It also has a list of all the [parks that allow/disallow dogs](http://ottawa.ca/rec_culture/park_facility/parks/dogs/index_en.html) split over five pages.

For my application I wanted to use that information, but there was no easily available place to get that information except through the city’s HTML tables on their web site (hence the need for open data).

I set out to extract all the information into a format that could be easily used for my application. The whole process probably took me about ten hours to complete. Here is a very general run-down of what I had to do to get the data in a decent, workable state.

### Ottawa Parks Data Set Process

Originally I had wanted to do an automated screen scrape of the data, but after looking through it I felt that it was way too inconsistent to allow for anything totally automated.

So, I resorted to a slightly less elegant and slightly more manual method:

1. I started with this list of dog parks: <http://ottawa.ca/rec_culture/park_facility/parks/dogs/index_en.html>).

2. I opened each of the HTML tables in its print view and saved them to my desktop.

3. I then opened those HTML files in Microsoft Excel, which parsed them into a fairly usable spreadsheet.

4. Some of the tables had the addresses in the neighbouring cell and some had it in the cell below. So, I corrected all the addresses and put them in the neighbouring cell.

5. I then had a list of some of the city parks, but not all. So I browsed, printed and saved the master list: <http://ottawa.ca/rec_culture/park_facility/parks/locations/index_en.html> (Thankfully the master list had the addresses in the proper orientation.)

6. I then merged the two lists together in my Excel sheet and removed duplicates.

7. Now, I needed to parse the dog related information into something machine readable. I did that sort of manually by reading the dog information and using a series of cells, I entered 1 or 0 for each of the parks.

	I also went through and augmented the information with the generalized info on the city’s web site like: ‘Rideau: Dogs on leash are permitted in parks’. In this case, I found all the Rideau parks and put that dogs were allowed, but required leashes.

8. At this point I had a huge list, but with a few major defects: almost everything was in ALL-CAPS (why would the city do that?) and I didn’t have any geo-location data for the parks, so they couldn’t be mapped easily.

9. To solve the ALL-CAPS, I copied the offending columns into the wonderful TextMate and ran the ‘Convert to Title Case’ action on them (its not perfect, but much better than ALL-CAPS). And then pasted them back into my spreadsheet.

10. Now for geo-location. I did some googling and found this batch geo-coding service, [http://www.batchgeo.com/](http://www.batchgeo.com/), that coincidentally allows you to past a spreadsheet of addresses and it will geo-code them all for you. Sweet!

11. An Excel spreadsheet is all jim-dandy but not very good for development purposes, so now I had to get my data out of Excel and into something I could use.

	I originally decided I wanted it in a SQLite database, so I exported from Excel to CSV, which I could then import to SQLite. That may have sounded easy, but was far from it. Excel’s CSV output is far from optimal, so it took a bunch of validating and re-importing until the data was ready to go.

12. I am now about six—seven hours in and feeling pretty excited, so I packaged it up into a little repo with a couple Python scripts for extracting the SQLite data into other formats (CSV, XML and JSON) and released the data set into [GitHub](https://github.com/thomasjbradley/ottawaparks), tweeted it and went to bed.

13. The next morning I got an e-mail that my data was being used in an Open Data Ottawa app (great!) but at the same time there was an issue opened on GitHub with my data. Apparently a whack load of the latitudes/longitudes all pointed to the same location (what I realized later was city hall).

	So off I go again trying to determine what was up. It turned out that the offending parks had addresses specified with intersections (and often many intersections). So I had to go through all those parks and correct their addresses and re—geo-code all those parks.

14. Upload to GitHub. Done. (Well done isn’t really final because I found an issue tonight with random extra quotes, but anyways.)

So that, in a (very large) nut shell, is my adventure in producing the [Ottawa Parks data set](https://github.com/thomasjbradley/ottawaparks), now onto what I am going to use if for.

## Ottawa Dog Park Finder

The application idea was actually my wife’s from a couple years ago, you can actually still [see the original announcement blog post](http://ottawadogblog.ca/2008/06/coming-soon-ottawa-dog-park-finder/). We didn’t get very far on it because adding parks in was really time consuming and there weren't any automated geo-location services at the time, it was all pretty manual.

So, I am restarting this application, but adding in a few new features.

The app is basically going to allow you to find parks in the city and whether they allow dogs on or off leash and other dog related information. It will be integrated with Google Maps and will allow you to enter locations and find parks closest to a specific location. And the app will hopefully allow users to vote on various aspects of the parks.

Wish me luck, because I only have a few days left.
