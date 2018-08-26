---
swagger: "2.0"
x-collection-name: Amadeus
x-complete: 0
info:
  title: Amadeus Get Points Of Interest Yapq Search Circle
  description: "Amadeus has partnered with YapQ to bring you point of interest APIs
    with the goal of offering you unbiased ratings of landmarks and tourist attractions.
    YapQ rates places according to their interest on social media and provides Wikipedia
    content and Geonames ID at a given location. \nYapQ's service indexes millions
    of points around the world, and provides content in 12 different languages. This
    allows you to ensure you catch the must-see sights at a specific YapQ supported
    location.\nEach point of interest comes with links to content, grading information,
    location and directions to help make discovering your destination easy and fun.\nThis
    service is still under active development, and the response format may change
    without warning. We'd be interested in your feedback - send us an email."
  contact:
    name: Amadeus Innovation and Research
    url: https://sandbox.amadeus.com
  version: 1.0.0
host: api.sandbox.amadeus.com
basePath: /v1.2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /cars/search-circle:
    get:
      summary: Get Cars Search
      description: "With this API you can find out the price and type of car, for
        all car rental providers, in a specified geographical location.\n\nYou can
        quickly see the locations of car providers near a given point, and what cars
        are available to rent, and at what prices. This API is based on our car pricing
        service that gets live availability from car providers, and is used to power
        a variety of airline and travel agency websites.\n           \nResults are
        validated from car providers, and thus response times may take up to 10 seconds
        (response times are typically about 5s), and the number of concurrent calls
        is throttled per user to avoid flooding our provider's systems. However, this
        means the final result is guaranteed to be live and accurate.\n\nThe configuration
        of this API allows search for car rentals in the rental location where the
        car is picked up (at the start of the rental), is the same as the one where
        it will be dropped off."
      operationId: getCarsSearchCircle
      x-api-path-slug: carssearchcircle-get
      parameters:
      - in: query
        name: currency
        description: The preferred currency to use when displaying prices and rates
          related to the car rental
      - in: query
        name: drop_off
        description: Date at which the car rental will end and the car will be returned
          to the rental location
      - in: query
        name: lang
        description: The preferred language of the content related to each car rental
      - in: query
        name: latitude
        description: Latitude of the center of the search
      - in: query
        name: longitude
        description: Longitude of the center of the search
      - in: query
        name: pick_up
        description: Date on which the car rental will be collected from the car rental
          location
      - in: query
        name: provider
        description: 2 character car rental provider code
      - in: query
        name: radius
        description: Radius around the center to look for hotels in kilometers (km)
      - in: query
        name: rate_class
        description: Allows to request specific rate types
      - in: query
        name: rate_filter
        description: Defines the types of rates to be returned in the output
      - in: query
        name: rate_plan
        description: Qualifies the rate depending on the pickup date and the rental
          duration
      - in: query
        name: vehicle
        description: Specifies the type of vehicle to be rented
      responses:
        200:
          description: OK
      tags:
      - Cars
      - Search
      - Circle
  /hotels/search-circle:
    get:
      summary: Get Hotels Search Circle
      description: "A fast Hotel shopping API to see which hotels are available in
        a given area, on a given day and displays their lowest prices. With this API
        you can find out the price of the cheapest daily rate for all hotels within
        a specified radius of a point.\n\nThis API allows you to quickly see the hotel
        locations in a region, and what prices in that area look like,  as well as
        the check-in and check-out dates, and get list of up to 140 properties (names,
        codes, image, amenities) with their locations and rates. Optional parameters
        such as currency and maximum rates, amenities or hotel chain codes are also
        available and can be used to narrow down the results. More optional parameters
        such as show_sold_out & rooms can be used to show sold out rooms and all available
        rooms. \n\nThe API is based on our high-speed hotel pricing cache, which is
        also used to power the Amadeus Hotel Search Engine application. Results are
        returned very quickly, response times are generally under 2s. Our cache has
        great global coverage and is constantly refreshed with the latest prices."
      operationId: getHotelsSearchCircle
      x-api-path-slug: hotelssearchcircle-get
      parameters:
      - in: query
        name: all_rooms
        description: This option if enabled will return all hotel room rates, not
          just the lowest room rate
      - in: query
        name: amenity
        description: Hotel amenities filter to search narrow down hotels with certain
          amenities
      - in: query
        name: chain
        description: Narrows the hotel search to a given hotel provider
      - in: query
        name: check_in
        description: Date on which the guest will begin their stay in the hotel
      - in: query
        name: check_out
        description: Date on which the guest will end their stay in the hotel
      - in: query
        name: currency
        description: The preferred currency for the results
      - in: query
        name: lang
        description: The preferred language of the content related to each hotel
      - in: query
        name: latitude
        description: Latitude of the center of the search
      - in: query
        name: longitude
        description: Longitude of the center of the search
      - in: query
        name: max_rate
        description: The maximum amount per night that any hotel in the shopping response
          should cost
      - in: query
        name: number_of_results
        description: The maximum number of hotels to return in the results set
      - in: query
        name: radius
        description: Radius around the center to look for hotels in kilometers (km)
      - in: query
        name: show_sold_out
        description: This option if enabled will return hotel names and addresses
          even if rooms are sold out (closed properties)
      responses:
        200:
          description: OK
      tags:
      - Hotels
      - Search
      - Circle
  /points-of-interest/yapq-search-circle:
    get:
      summary: Get Points Of Interest Yapq Search Circle
      description: "Amadeus has partnered with YapQ to bring you point of interest
        APIs with the goal of offering you unbiased ratings of landmarks and tourist
        attractions. YapQ rates places according to their interest on social media
        and provides Wikipedia content and Geonames ID at a given location. \nYapQ's
        service indexes millions of points around the world, and provides content
        in 12 different languages. This allows you to ensure you catch the must-see
        sights at a specific YapQ supported location.\nEach point of interest comes
        with links to content, grading information, location and directions to help
        make discovering your destination easy and fun.\nThis service is still under
        active development, and the response format may change without warning. We'd
        be interested in your feedback - send us an email."
      operationId: getPointsOfInterestYapqSearchCircle
      x-api-path-slug: pointsofinterestyapqsearchcircle-get
      parameters:
      - in: query
        name: category
        description: Filters the resulting points_of_interest to include only results
          which have a least one category containing the given provided word
      - in: query
        name: geonames
        description: Setting this to true includes only points of interest with a
          geonames ID
      - in: query
        name: image_size
        description: The size of the images youd like to see in the response
      - in: query
        name: lang
        description: The preferred language of the content related to each point of
          interest
      - in: query
        name: latitude
        description: Latitude of the center of the search, in decimal degrees
      - in: query
        name: longitude
        description: Longitude of the center of the search, in decimal degrees
      - in: query
        name: number_of_images
        description: Number of images to display
      - in: query
        name: number_of_results
        description: The maximum number of points of interest to return in the results
          set
      - in: query
        name: radius
        description: Radius around the center to look for points-of-interest around
          the given latitude and longitude in kilometers (km)
      - in: query
        name: social_media
        description: Enabling this includes images from Instagram in the output results
      - in: query
        name: vibes
        description: Includes content that doesnt correspond to an active physical
          place, but which gives the user some background information, or vibe for
          the place they are visiting
      responses:
        200:
          description: OK
      tags:
      - Points
      - Of
      - Interest
      - Yapq
      - Search
      - Circle
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---