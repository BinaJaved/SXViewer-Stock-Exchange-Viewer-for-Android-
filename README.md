# SXViewer-Stock Exchange Viewer for Android

***General Description***
The development of the Stock Exchange Viewer (SXViewer) android app is revolutionary. SXViewer brings companies and investors together by providing the stock exchange details in one place. SXViewer pulls stock data from data Yahoo Finance Service and displays the detailed view of each stock together with interactive charts. With SXViewer, users can have a list of favorite stocks, in order to monitor the interested stock quotes change frequently. SXViewer development turns out to be the grand accomplishment for business professionals.

***Implementation Details***
SXViewer is implemented in C# using Xamarin (Mono for Android), which is a common platform for developing Android applications. It had provided a Visual Studio add-in for Android Application development. By using Visual Studio, we prepared the prototype of the application and implemented screens, Webservice and database in C#.

SXViewer extracts real-time stocks data from Yahoo Finance Webservice. 

The source code has been divided into three parts, "SXViewer", “SXViewerCore” and “FinanceWebServide”. 

*SXViewerCore*
SXViewerCore project is heart of program, it implements all core classes. SXViewerCore project is further divided into two sub-parts; namely Data Layer and Business Layer.
Data Layer contains the SQLite database C# code.
Business Layer contains the Stocks and StockManager classes (C# code).

*Yahoo Finance Web Service:*
We used a .NET Web Service to get real time stock data. Web Services plays an important role to talk to an external database whatever the database is. To store data into Mobile, we can use Android's light Database - SQLite. In order to talk to external remote database, we need a Web Service to talk to database. 

Web Methods from SXViewer Application:
-StockExists 
-GetStockQuote
-GetStockChart 

GetStockQuotes(): Send multiple stocks in a comma separated string and pass it as a parameter. This will return the XML of all the Stocks.

StockExist(): Send multiple stock scripts in a comma separated string and pass it as a parameter. This will return the "Exchange" of the Stock. If a stock script is Invalid, the XML will return "NA" (Not Applicable). 

GetStockChart(): shows the chart of a stock according to the chart parameters. 
These Web Methods were sufficient to create Market Watch for All Exchange Stock. Though web service is an important layer to fetch stock details in this Application, URL provided is used for Proof of Concept. To consume Web Methods, we add a Web Reference to stock service.

SQLite
SQLite is a relational database management system contained in a small C programming library. SQLite is not a separate process that is accessed from the client application, but is an integral part of it. SQLite is popular choice as an embedded database for local/client storage in application software such as web browsers, Mobile Device, Tablet PC. 

In “SXViewer" application,  database has one single Table with subsequent methods to Fetch, Add and Delete stocks that are used in  Market Watch - Favourite List.
The two classes, stock and stock manager, one we will be for creating a Data Repository and other for all Database Operations.
SqLite Helper class used to do all database operations. The code is self explained and nothing much within the code to detail. 
Only one Table was used for adding custom stock script. 

*SXViewer*
“SXViewer” implements Android User Interface and also calls the core functionality written in “SXViewerCore” project. 
It has below three sub-folders:
Drawable: containing all graphic contents e.g. images 
Layout: contains all layouts (screens we see in Android Application)
Values: Global variables that we will use throughout the application 
The step by step method of creating Professional Android Application is shown below, we built primarily five screens: 
-Splash Screen  
-Market Watch  
-Stock Script Detail View 
-Add Stock  
-Get Stock Quote 
-Show Stock Chart
