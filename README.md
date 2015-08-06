## Agility-Stream
#####An Event Tracker App For Agile Teams

Keeping track of agile software projects is hard. Let’s create an activity feed that can bring it all together. After creating an account on the site I can:

- Create a project
- Register one Pivotal Tracker project
- Register one GitHub project
- Integrate with CircleCI
- Generate a unique email address for this feed
- Then, while working on the project:

Changes from the project management tool (stories added, completed, comments, etc) are reflected in the feed
Activity from GitHub (pushes, issues, etc) is reflected in the feed
Any emails sent to the project-specific address show up in the feed
Build status updates from CircleCI show up in the feed
The board displays some highlights from the team’s achievement this week
Given that our team is super-agile and constantly pushing code, these events have smart aggregation. If the same person pushes code three times within a few hours, Agility Stream only displays one event in the stream that links to all three commits. Or delivering two features in Tracker shows up as just one entry with two links.

###Technical Requirements

####Caching and Data Querying

The app will take advantage of caching and performance techniques including:

- data caching
- query consolidation
- database optimizations (query count, using indicies, joins)

####Background Workers

The app will make extensive use of background workers including:

- Sending or receiving email
- Querying and fetching data from third-party APIs
- Processing bulk data

####Providing an API & Gem

The main functionality of the application will be available through an API. That API will come with a wrapper gem that makes it easy to work with.

The background workers will not connect to the application database directly or load the Rails environment for the app. They must go through the API gem to read from and write to feeds.

####Client App

An Angular app (With Material Angular) will be built as a client-side application that consumes the API


