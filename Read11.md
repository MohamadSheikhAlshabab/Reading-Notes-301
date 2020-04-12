# Read-11:

--------------

## EJS:


 - ### Use EJS to Template Your Node Application:
 
  - EJS Partials footer.ejs, head.ejs, header.ejs:
   -  call those partials and define three files we'll use across all of our site: head.ejs, header.ejs, and footer.ejs
   
   - <!-- views/partials/head.ejs -->
<meta charset="UTF-8">
<title>Super Awesome</title>

<!-- CSS (load bootstrap from a CDN) -->
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<style>
    body    { padding-top:50px; }
</style>
<!-- views/partials/header.ejs -->

<nav class="navbar navbar-default" role="navigation">
<div class="container-fluid">

    <div class="navbar-header">
        <a class="navbar-brand" href="#">
            <span class="glyphicon glyphicon glyphicon-tree-deciduous"></span>
            EJS Is Fun
        </a>

        <ul class="nav navbar-nav">
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
        </ul>
    </div>

</div>
</nav>
<!-- views/partials/footer.ejs -->
<p class="text-center text-muted">© Copyright 2014 The Awesome People</p>

- Using EJS Partials :
  -  The syntax to use an EJS partial is: <% include FILENAME %>
- Single Variable:
  - To echo a single variable, we just use <%= tagline %>.
  
- Looping Over Data
  - To loop over our data, we will use .forEach

- Conclusion
  - EJS let's us spin up quick applications when we don't need anything too complex.
  - By using partials and having the ability to easily pass variables to our views, we can build some great applications quickly.
  
 ---------
 ### Using the API:
 
  - Here's how to determine which of those options to use:
   1. If the request requires authorization (such as a request for an individual's private data), then the application must provide an OAuth 2.0 token with the request.
    -The application may also provide the API key, but it doesn't have to.
  2. If the request doesn't require authorization (such as a request for public data), then the application must provide either the API key or an OAuth 2.0 token, or both—whatever option is most convenient for you.
  
  - Authorizing requests with OAuth 2.0:
   1. When you create your application, you register it using the Google API Console. Google then provides information you'll need later, such as a client ID and a client secret.
   2. Activate the Books API in the Google API Console.
   3. When your application needs access to user data, it asks Google for a particular scope of access.
   4. Google displays a consent screen to the user, asking them to authorize your application to request some of their data.
   5. If the user approves, then Google gives your application a short-lived access token.
   6. Your application requests user data, attaching the access token to the request.
   7. If Google determines that your request and the token are valid, it returns the requested data.
   
   - Here's the OAuth 2.0 scope information for the Books API: [link](https://www.googleapis.com/auth/books)
   
  - Acquiring and using an API key:
   1. Open the Credentials page in the API Console.[link](https://console.developers.google.com/apis/credentials?pli=1)
   2. This API supports two types of credentials. Create whichever credentials are appropriate for your project:
     - OAuth 2.0: Whenever your application requests private user data, it must send an OAuth 2.0 token along with the request. Your application first sends a client ID and, possibly, a client secret to obtain a token. You can generate OAuth 2.0 credentials for web applications, service accounts, or installed applications.
     - API keys: A request that does not provide an OAuth 2.0 token must send an API key. The key identifies your project and provides API access, quota, and reports
     [To keep your API keys secure](https://cloud.google.com/docs/authentication/api-keys)
     
   - Google Books IDs:
     - Volume IDs - Unique strings given to each volume that Google Books knows about. An example of a volume ID is _LettPDhwR0C. You can use the API to get the volume ID by making a request that returns a Volume resource; you can find the volume ID in its id field.
     - Bookshelf IDs - Numeric values given to a bookshelf in a user's library. Google provides some pre-defined shelves for every user with the following IDs:
         - Favorites: 0
         - Purchased: 1
         - To Read: 2
         - Reading Now: 3
         - Have Read: 4
         - Reviewed: 5
         - Recently Viewed: 6
         - My eBooks: 7
         - Books For You: 8 If we have no recommendations for the user, this shelf does not exist.
     - User IDs - Unique numeric values assigned to each user. These values are not necessarily the same ID value used in other Google services. Currently, the only way retrieve the user ID is to extract it from the selfLink in a Bookshelf resource retrieved with an authenticated request. Users can also obtain their own user ID from the Books site. A user cannot obtain the user ID for another user via the API or the Books site; the other user would have to share that information explicitly, by email for example.
     
     - Optional query parameters:
     [ standard query parameters](https://developers.google.com/books/docs/v1/using#st_params)
       - Download Format: You use the download parameter to restrict the returned results to volumes that have an available download format of epub by setting the to the value epub.
       - Filtering:You can use the filter parameter to restrict the returned results further by setting it the to one of the following values:
          - partial 
          - Returns results where at least parts of the text are previewable.
          - full - Only returns results where all of the text is viewable.
          - free-ebooks - Only returns results that are free Google eBooks.
          - paid-ebooks - Only returns results that are Google eBooks with a price.
          - ebooks - Only returns results that are Google eBooks, paid or free.
          Examples of non-eBooks would be publisher content that is available in limited preview and not for sale, or magazines.
          
       - Pagination: You can paginate the volumes list by specifying two values in the parameters for the request:   
           - startIndex - The position in the collection at which to start. The index of the first item is 0.
           - maxResults - The maximum number of results to return. The default is 10, and the maximum allowable value is 40.
       - Print Type: You can use the printType parameter to restrict the returned results to a specific print or publication type by setting it to one of the following values:    
          - all - Does not restrict by print type (default).
          - books - Returns only results that are books.
          - magazines - Returns results that are magazines.
       - Projection: You can use the projection parameter with one of the following values to specify a predefined set of Volume fields to return:   
          - full - Returns all Volume fields.
          - lite - Returns only certain fields. See field descriptions marked with double asterisks in the Volume reference to find out which fields are included.
       - Sorting: By default, a volumes search request returns maxResults results, where maxResults is the parameter used in pagination (above), ordered by relevance to search terms.
          - relevance - Returns results in order of the relevance of search terms (this is the default).
          - newest - Returns results in order of most recently to least recently published.
          
