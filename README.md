# GraphQL-Server

GraphQL Server with custom endpoint.

This configuration is using [graphql-yoga](https://github.com/prisma/graphql-yoga).

graphql-yoga is a fully-featured GraphQL Server with focus on easy setup, performance & great developer experience.

The great thing about graphql-yoga is the fact that it comes with a playground client to run queries and mutations on the browser.

## Configuring the GraphQL server

We will be using this server to fetch weather data from a REST API. But the endpoint can be changed to retrieve data from any REST API.

* Clone this repo to your local machine.

```
git clone https://github.com/jtaylor1989/GraphQL-Server.git

cd GraphQL-Server
```


## Running the application

* Install client dependencies.

```
yarn

# or

npm install
```

* Launch the localhost.

```
npm start
```
You can now navigate to: http://localhost:4000/ and start using the Playground Client by running queries following the GraphQL schema defined in `src/graphql.schema` in this project folder.

## Example: running a GraphQL query to fetch weather data.

Copy and paste the following query to get the weather forecast for the city of Paris for the next days.

```
{
  getForecast(woeid: 615702) {
    title
    timezone
    consolidated_weather {
      applicable_date
      weather_state_name
      the_temp
      min_temp
      max_temp
      wind_speed
      humidity
      visibility
      air_pressure
    }
  }
}
```

You should see the following results.

<img width="1437" alt="Playground" src="https://user-images.githubusercontent.com/26605247/55567572-dc080480-56f5-11e9-9fbf-066dc8a1de02.png">

Now this GraphQL server is ready to be integrated with a GraphQL Client of your choice. You only need to pass the url endpoint to your client.

For more info, check the following [repo](https://github.com/jtaylor1989/Weather-Apollo-Client) to see how to connect this back end to a React Native app using the Apollo GraphQL Client.
