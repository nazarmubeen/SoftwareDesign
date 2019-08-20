This article is first one from the series of articles dedicated to system design interviews. Here i am going to present the base scenario to consider before starting to solve system design problems.

Questions to ask?

1) what is the number of requests a website will recieve in a day/month/second?
2) what is the amount of memory a website will deal in a day/month/second?
3) what is the number of servers that can accomodate these requests?

To answer this , first we need to remember the below numbers:-

1 million = 10 lakh = 1000000 = 10^6
1 billion = 1000 million = 10^9

1 KB = 1024 B = 10^3
1 MB= 10^6 = 1024 KB
1 GB= 10^9 = 1024 MB
1 TB = 10^12 = 1024 GB

Memory we need to see in Bytes
Requests we need to see in numbers

example :-

suppose a website recieves 100M requests every month then:-

requests per day = request per month /24 = 416700 requests
requests per second = requests per day / (24*3600) = 4.8 requests per second

memory:-

if we take 20:80 principal where 20 percent is write and 80 percent is read operation. From above example it will be like 100 M requests for write then 400 M is read request.

For each second we are writing 4.8 requests if we consider data to write is 500kb then total data writing of 2400 kb or 2.4 Mb data per second.

For each second we are also reading around 9.6 MB of data. So bandwidth is approximately 12 Mb second.

Storage:-

if we consider for 5 years and 2.4MB of data is written at every second then :-

2.4 MB per second = 207360 MB per day = 207 GB per day= 4.9 TB per month = 59 TB per year = 295 TB for 5 year.

We will go through in detail about 500 kb data that we are writing in next chapters.

So it will be around 295 TB of data. If we consider one machine :-
with win 32 w/NTFS we can store 2TB data ,so total 147 machine we need to store all this data.
With solaris 9/10 we need only 18 machines /( 18 TB in each machine)

we can divide these machines into cache data and db data based upon requirement.

User storage and cache storage is coming up in next tutorial.
