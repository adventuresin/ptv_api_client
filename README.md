# ptv_api_client
The PTV Timetable API provides direct access to Public Transport Victoria’s public transport timetable data.    The API returns scheduled timetable, route and stop data for all metropolitan and regional train, tram and bus services in Victoria, including Night Network(Night Train and Night Tram data are included in metropolitan train and tram services data, respectively, whereas Night Bus is a separate route type).    The API also returns real-time data for metropolitan train, tram and bus services (where this data is made available to PTV), as well as disruption information, stop facility information, and access to myki ticket outlet data.    This Swagger is for Version 3 of the PTV Timetable API. By using this documentation you agree to comply with the licence and terms of service.    Train timetable data is updated daily, while the remaining data is updated weekly, taking into account any planned timetable changes (for example, due to holidays or planned disruptions). The PTV timetable API is the same API used by PTV for its apps. To access the most up to date data PTV has (including real-time data) you must use the API dynamically.    You can access the PTV Timetable API through a HTTP or HTTPS interface, as follows:        base URL / version number / API name / query string  The base URL is either:    *  http://timetableapi.ptv.vic.gov.au  or    *  https://timetableapi.ptv.vic.gov.au    The Swagger JSON file is available at http://timetableapi.ptv.vic.gov.au/swagger/docs/v3    Frequently asked questions are available on the PTV website at http://ptv.vic.gov.au/apifaq    Links to the following information are also provided on the PTV website at http://ptv.vic.gov.au/ptv-timetable-api/  * How to register for an API key and calculate a signature  * PTV Timetable API V2 to V3 Migration Guide  * Documentation for Version 2 of the PTV Timetable API  * PTV Timetable API Data Quality Statement    All information about how to use the API is in this documentation. PTV cannot provide technical support for the API.    Credits: This page has been based on Steve Bennett's http://opentransportdata.org/, used with permission.  

This Dart package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: v3
- Build package: org.openapitools.codegen.languages.DartClientCodegen
For more information, please visit [http://ptv.vic.gov.au/digital](http://ptv.vic.gov.au/digital)

## Requirements

Dart 1.20.0 or later OR Flutter 0.0.20 or later

## Installation & Usage

### Github
If this Dart package is published to Github, please include the following in pubspec.yaml
```
name: ptv_api_client
version: 0.0.1
description: OpenAPI API client for the Public Transport Victoria public API
dependencies:
  ptv_api_client:
    git: https://github.com/GIT_USER_ID/GIT_REPO_ID.git
      version: 'any'
```

### Local
To use the package in your local drive, please include the following in pubspec.yaml
```
dependencies:
  ptv_api_client:
    path: /path/to/ptv_api_client
```

## Tests

TODO

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```dart
import 'package:ptv_api_client/api.dart';


var api_instance = DeparturesApi();
var routeType = 56; // int | Number identifying transport mode; values returned via RouteTypes API
var stopId = 56; // int | Identifier of stop; values returned by Stops API
var platformNumbers = []; // List<int> | Filter by platform number at stop
var directionId = 56; // int | Filter by identifier of direction of travel; values returned by Directions API - /v3/directions/route/{route_id}
var lookBackwards = true; // bool | Indicates if filtering runs (and their departures) to those that arrive at destination before date_utc (default = false). Requires max_results &gt; 0.
var gtfs = true; // bool | Indicates that stop_id parameter will accept \"GTFS stop_id\" data
var dateUtc = 2013-10-20T19:20:30+01:00; // DateTime | Filter by the date and time of the request (ISO 8601 UTC format) (default = current date and time)
var maxResults = 56; // int | Maximum number of results returned
var includeCancelled = true; // bool | Indicates if cancelled services (if they exist) are returned (default = false) - metropolitan train only
var expand = []; // List<String> | List objects to be returned in full (i.e. expanded) - options include: all, stop, route, run, direction, disruption
var token = token_example; // String | Please ignore

try {
    var result = api_instance.departuresGetForStop(routeType, stopId, platformNumbers, directionId, lookBackwards, gtfs, dateUtc, maxResults, includeCancelled, expand, token);
    print(result);
} catch (e) {
    print("Exception when calling DeparturesApi->departuresGetForStop: $e\n");
}

```

## Documentation for API Endpoints

All URIs are relative to *http://timetableapi.ptv.vic.gov.au*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DeparturesApi* | [**departuresGetForStop**](docs//DeparturesApi.md#departuresgetforstop) | **GET** /v3/departures/route_type/{route_type}/stop/{stop_id} | View departures for all routes from a stop
*DeparturesApi* | [**departuresGetForStopAndRoute**](docs//DeparturesApi.md#departuresgetforstopandroute) | **GET** /v3/departures/route_type/{route_type}/stop/{stop_id}/route/{route_id} | View departures for a specific route from a stop
*DirectionsApi* | [**directionsForDirection**](docs//DirectionsApi.md#directionsfordirection) | **GET** /v3/directions/{direction_id} | View all routes for a direction of travel
*DirectionsApi* | [**directionsForDirectionAndType**](docs//DirectionsApi.md#directionsfordirectionandtype) | **GET** /v3/directions/{direction_id}/route_type/{route_type} | View all routes of a particular type for a direction of travel
*DirectionsApi* | [**directionsForRoute**](docs//DirectionsApi.md#directionsforroute) | **GET** /v3/directions/route/{route_id} | View directions that a route travels in
*DisruptionsApi* | [**disruptionsGetAllDisruptions**](docs//DisruptionsApi.md#disruptionsgetalldisruptions) | **GET** /v3/disruptions | View all disruptions for all route types
*DisruptionsApi* | [**disruptionsGetDisruptionById**](docs//DisruptionsApi.md#disruptionsgetdisruptionbyid) | **GET** /v3/disruptions/{disruption_id} | View a specific disruption
*DisruptionsApi* | [**disruptionsGetDisruptionModes**](docs//DisruptionsApi.md#disruptionsgetdisruptionmodes) | **GET** /v3/disruptions/modes | Get all disruption modes
*DisruptionsApi* | [**disruptionsGetDisruptionsByRoute**](docs//DisruptionsApi.md#disruptionsgetdisruptionsbyroute) | **GET** /v3/disruptions/route/{route_id} | View all disruptions for a particular route
*DisruptionsApi* | [**disruptionsGetDisruptionsByRouteAndStop**](docs//DisruptionsApi.md#disruptionsgetdisruptionsbyrouteandstop) | **GET** /v3/disruptions/route/{route_id}/stop/{stop_id} | View all disruptions for a particular route and stop
*DisruptionsApi* | [**disruptionsGetDisruptionsByStop**](docs//DisruptionsApi.md#disruptionsgetdisruptionsbystop) | **GET** /v3/disruptions/stop/{stop_id} | View all disruptions for a particular stop
*OutletsApi* | [**outletsGetAllOutlets**](docs//OutletsApi.md#outletsgetalloutlets) | **GET** /v3/outlets | List all ticket outlets
*OutletsApi* | [**outletsGetOutletsByGeolocation**](docs//OutletsApi.md#outletsgetoutletsbygeolocation) | **GET** /v3/outlets/location/{latitude},{longitude} | List ticket outlets near a specific location
*PatternsApi* | [**patternsGetPatternByRun**](docs//PatternsApi.md#patternsgetpatternbyrun) | **GET** /v3/pattern/run/{run_id}/route_type/{route_type} | View the stopping pattern for a specific trip/service run
*RouteTypesApi* | [**routeTypesGetRouteTypes**](docs//RouteTypesApi.md#routetypesgetroutetypes) | **GET** /v3/route_types | View all route types and their names
*RoutesApi* | [**routesOneOrMoreRoutes**](docs//RoutesApi.md#routesoneormoreroutes) | **GET** /v3/routes | View route names and numbers for all routes
*RoutesApi* | [**routesRouteFromId**](docs//RoutesApi.md#routesroutefromid) | **GET** /v3/routes/{route_id} | View route name and number for specific route ID
*RunsApi* | [**runsForRoute**](docs//RunsApi.md#runsforroute) | **GET** /v3/runs/route/{route_id} | View all trip/service runs for a specific route ID
*RunsApi* | [**runsForRouteAndRouteType**](docs//RunsApi.md#runsforrouteandroutetype) | **GET** /v3/runs/route/{route_id}/route_type/{route_type} | View all trip/service runs for a specific route ID and route type
*RunsApi* | [**runsForRun**](docs//RunsApi.md#runsforrun) | **GET** /v3/runs/{run_id} | View all trip/service runs for a specific run ID
*RunsApi* | [**runsForRunAndRouteType**](docs//RunsApi.md#runsforrunandroutetype) | **GET** /v3/runs/{run_id}/route_type/{route_type} | View the trip/service run for a specific run ID and route type
*SearchApi* | [**searchSearch**](docs//SearchApi.md#searchsearch) | **GET** /v3/search/{search_term} | View stops, routes and myki ticket outlets that match the search term
*StopsApi* | [**stopsStopDetails**](docs//StopsApi.md#stopsstopdetails) | **GET** /v3/stops/{stop_id}/route_type/{route_type} | View facilities at a specific stop (Metro and V/Line stations only)
*StopsApi* | [**stopsStopsByGeolocation**](docs//StopsApi.md#stopsstopsbygeolocation) | **GET** /v3/stops/location/{latitude},{longitude} | View all stops near a specific location
*StopsApi* | [**stopsStopsForRoute**](docs//StopsApi.md#stopsstopsforroute) | **GET** /v3/stops/route/{route_id}/route_type/{route_type} | View all stops on a specific route


## Documentation For Models

 - [V3BulkDeparturesRequest](docs//V3BulkDeparturesRequest.md)
 - [V3BulkDeparturesResponse](docs//V3BulkDeparturesResponse.md)
 - [V3BulkDeparturesRouteDirectionResponse](docs//V3BulkDeparturesRouteDirectionResponse.md)
 - [V3BulkDeparturesStopResponse](docs//V3BulkDeparturesStopResponse.md)
 - [V3BulkDeparturesUpdateResponse](docs//V3BulkDeparturesUpdateResponse.md)
 - [V3Departure](docs//V3Departure.md)
 - [V3DeparturesBroadParameters](docs//V3DeparturesBroadParameters.md)
 - [V3DeparturesResponse](docs//V3DeparturesResponse.md)
 - [V3DeparturesSpecificParameters](docs//V3DeparturesSpecificParameters.md)
 - [V3Direction](docs//V3Direction.md)
 - [V3DirectionWithDescription](docs//V3DirectionWithDescription.md)
 - [V3DirectionsResponse](docs//V3DirectionsResponse.md)
 - [V3Disruption](docs//V3Disruption.md)
 - [V3DisruptionDirection](docs//V3DisruptionDirection.md)
 - [V3DisruptionMode](docs//V3DisruptionMode.md)
 - [V3DisruptionModesResponse](docs//V3DisruptionModesResponse.md)
 - [V3DisruptionResponse](docs//V3DisruptionResponse.md)
 - [V3DisruptionRoute](docs//V3DisruptionRoute.md)
 - [V3DisruptionStop](docs//V3DisruptionStop.md)
 - [V3Disruptions](docs//V3Disruptions.md)
 - [V3DisruptionsResponse](docs//V3DisruptionsResponse.md)
 - [V3ErrorResponse](docs//V3ErrorResponse.md)
 - [V3Outlet](docs//V3Outlet.md)
 - [V3OutletGeolocation](docs//V3OutletGeolocation.md)
 - [V3OutletGeolocationParameters](docs//V3OutletGeolocationParameters.md)
 - [V3OutletGeolocationResponse](docs//V3OutletGeolocationResponse.md)
 - [V3OutletParameters](docs//V3OutletParameters.md)
 - [V3OutletResponse](docs//V3OutletResponse.md)
 - [V3ResultOutlet](docs//V3ResultOutlet.md)
 - [V3ResultRoute](docs//V3ResultRoute.md)
 - [V3ResultStop](docs//V3ResultStop.md)
 - [V3Route](docs//V3Route.md)
 - [V3RouteDeparturesSpecificParameters](docs//V3RouteDeparturesSpecificParameters.md)
 - [V3RouteResponse](docs//V3RouteResponse.md)
 - [V3RouteServiceStatus](docs//V3RouteServiceStatus.md)
 - [V3RouteType](docs//V3RouteType.md)
 - [V3RouteTypesResponse](docs//V3RouteTypesResponse.md)
 - [V3RouteWithStatus](docs//V3RouteWithStatus.md)
 - [V3Run](docs//V3Run.md)
 - [V3RunResponse](docs//V3RunResponse.md)
 - [V3RunsResponse](docs//V3RunsResponse.md)
 - [V3SearchParameters](docs//V3SearchParameters.md)
 - [V3SearchResult](docs//V3SearchResult.md)
 - [V3Status](docs//V3Status.md)
 - [V3StopAccessibility](docs//V3StopAccessibility.md)
 - [V3StopAccessibilityWheelchair](docs//V3StopAccessibilityWheelchair.md)
 - [V3StopAmenityDetails](docs//V3StopAmenityDetails.md)
 - [V3StopBase](docs//V3StopBase.md)
 - [V3StopDepartureRequest](docs//V3StopDepartureRequest.md)
 - [V3StopDepartureRequestRouteDirection](docs//V3StopDepartureRequestRouteDirection.md)
 - [V3StopDetails](docs//V3StopDetails.md)
 - [V3StopGeosearch](docs//V3StopGeosearch.md)
 - [V3StopGps](docs//V3StopGps.md)
 - [V3StopLocation](docs//V3StopLocation.md)
 - [V3StopOnRoute](docs//V3StopOnRoute.md)
 - [V3StopResponse](docs//V3StopResponse.md)
 - [V3StopStaffing](docs//V3StopStaffing.md)
 - [V3StoppingPattern](docs//V3StoppingPattern.md)
 - [V3StopsByDistanceResponse](docs//V3StopsByDistanceResponse.md)
 - [V3StopsOnRouteResponse](docs//V3StopsOnRouteResponse.md)
 - [V3VehicleDescriptor](docs//V3VehicleDescriptor.md)
 - [V3VehiclePosition](docs//V3VehiclePosition.md)


## Documentation For Authorization

 All endpoints do not require authorization.


## Author



