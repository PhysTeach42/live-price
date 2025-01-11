Commonwealth Edison (Com Ed) is an energy company in Northern Illinois. It offers hourly pricing to incentivise the turning off of electrical appliances during peak demand. The website includes an API with prices every five minutes and returns a JSON with the previous 100 data pairs. The data includes the time in millis UTC and the pricer per kWh in cents.

I was interested in coding a web page that would request the data from the site (https://hourlypricing.comed.com/api?type=5minutefeed) I found some examples of code that would get the JSON data and put it in the console

My first obstacle was that in requesting the JSON, my request was blocked by a violation of the CORS policy I learned about using a proxy and tried several but couldn't get them to work. Finally, I stumbled upon CorsProxy.io. It somehow (?) connected with GitHub and attached a key for my account. This allowed me to overcome the CORS obstacle but then I had a new obstacle

The second obstacle was that there was a Content Security Policy that blocked the use of eval(). This seemed to come from using the function() in the $.getJSON(sampleURL.com, function(data) {}) jquery. I tried different libraries in the header but nothing seemed to work. Then I saw that fetch could be used without calling a library in the header and without using a function. This worked and allowed me to get the requested data to show in the console.

I am unfamiliar with the fetch functions/commands (such as .then) so my next goal is to learn how to use the fetch functions and how to put the data into the webpage.
