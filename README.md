# API Reverse Proxy

Did you get CORS error from your local environment?
And your API provider does not allowed to set 
then this is a solution for your case.


set your API_URL, and AUTH_HEADER in your .env file, then call
```docker-compose up --build```

then you'll get a host http://localhost:2020 as reverse proxy against your API!
