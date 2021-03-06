---
swagger: "2.0"
x-collection-name: BBC
x-complete: 0
info:
  title: BBC Nitro List all Master Brands
  description: List all Master Brands
  termsOfService: http://www.bbc.co.uk/terms/
  contact:
    name: Open Nitro Project
    url: http://developer.bbc.co.uk/
    email: nitro@bbc.co.uk
  version: 1.0.0
host: programmes.api.bbc.com
basePath: /nitro/api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /:
    get:
      summary: Get API definition
      description: Get API definition
      operationId: getAPI
      x-api-path-slug: get
      responses:
        200:
          description: OK
      tags:
      - ""
  /availabilities:
    get:
      summary: Discover details of on-demand availability for programmes and their
        versions
      description: Discover details of on-demand availability for programmes and their
        versions
      operationId: listAvailability
      x-api-path-slug: availabilities-get
      parameters:
      - in: query
        name: availability
        description: filter for subset of availabilities
      - in: query
        name: debug
        description: Turn on debug information (undocumented)
      - in: query
        name: descendants_of
        description: filter for subset of availabilities that have PID as ancestor
      - in: query
        name: media_set
        description: filter for subset of availabilities with media set
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: sort
        description: 'Sorts:* scheduled_start: sort chronologically by scheduled start
          time/date, ascending'
      - in: query
        name: sort_direction
        description: Sort direction
      - in: query
        name: territory
        description: filter for availabilities in given territory
      responses:
        200:
          description: OK
      tags:
      - Availabilities
  /broadcasts:
    get:
      summary: Build schedules and find metadata for TV and radio broadcasts
      description: Fetch metadata about linear Broadcasts and Services, allowing the
        generation of Television and Radio schedules and other datasets for broadcast
        items. Use /schedules instead of this feed as it is more efficient. Broadcasts
        will be deprecated in the future.
      operationId: listBroadcasts
      x-api-path-slug: broadcasts-get
      parameters:
      - in: query
        name: authority
        description: filter for subset of broadcasts that have given authority
      - in: query
        name: descendants_of
        description: filter for subset of broadcasts that are descendants of the given
          programme PID
      - in: query
        name: end_from
        description: filter for subset of broadcasts that end on or later than the
          specified datetime
      - in: query
        name: end_to
        description: filter for subset of broadcasts that end on or earlier than the
          specified datetime
      - in: query
        name: format
        description: filter for subset of broadcasts that are classified in the given
          format ID
      - in: query
        name: genre
        description: filter for subset of broadcasts that are classified in the given
          genre ID
      - in: query
        name: id
        description: filter for subset of broadcasts that have given identifier
      - in: query
        name: item
        description: filter for subset of broadcasts with the given item performed
          on it
      - in: query
        name: mixin
        description: 'Mixins:* titles: return ancestor programme titles'
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: people
        description: filter for subset of broadcasts that have given contributor
      - in: query
        name: pid
        description: filter for subset of broadcasts having given PID
      - in: query
        name: q
        description: filter for subset of broadcasts matching supplied keyword/phrase
          (boolean operators permitted)
      - in: query
        name: schedule_day
        description: filter for subset of broadcasts that start on the specified day
          (BBC time)
      - in: query
        name: schedule_day_from
        description: filter for subset of broadcasts that start on or after the specified
          day (BBC time)
      - in: query
        name: schedule_day_to
        description: filter for subset of broadcasts that start on or before the specified
          day (BBC time)
      - in: query
        name: service_master_brand
        description: filter for subset of broadcasts with given service master brand
      - in: query
        name: sid
        description: filter for subset of broadcasts that are on the specified linear
          service
      - in: query
        name: sort
        description: 'Sorts:* start_date: sort chronologically by scheduled start
          time/date, ascending'
      - in: query
        name: sort_direction
        description: Sort direction
      - in: query
        name: start_from
        description: filter for subset of broadcasts that start on or later than the
          specified datetime
      - in: query
        name: start_to
        description: filter for subset of broadcasts that start on or earlier than
          the specified datetime
      - in: query
        name: version
        description: filter for subset of broadcasts with given PID as their parent
          version
      responses:
        200:
          description: OK
      tags:
      - Broadcasts
  /groups:
    get:
      summary: 'Find metadata for curated groups: seasons, collections, galleries
        or franchises'
      description: Long-lived curated collections of programmes and more, including
        Collections, Seasons, Franchises and Galleries
      operationId: listGroups
      x-api-path-slug: groups-get
      parameters:
      - in: query
        name: embargoed
        description: Control return of embargoed items (undocumented)
      - in: query
        name: for_descendants_of
        description: filter for groups related to given programme or its descendants
      - in: query
        name: for_programme
        description: filter for subset of groups directly related to a given programme
      - in: query
        name: group
        description: filter for subset of groups which belong to the given group pid
      - in: query
        name: group_type
        description: filter for subset of groups that have the given group type
      - in: query
        name: member
        description: filter for subset of groups which contain an entity with the
          given pid as a member
      - in: query
        name: mixin
        description: 'Mixins:* alternate_images: mixin to return the alternate images
          for a group* group_for: mixin to return links to programme entities that
          group belongs to* images: mixin to add image information for a group* related_links:
          mixin to return related links for the group'
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: partner_id
        description: filter for groups by partner ID
      - in: query
        name: partner_pid
        description: filter for groups by partner PID
      - in: query
        name: pid
        description: filter for subset of seasons, collections, galleries or franchises
          having given PID
      - in: query
        name: q
        description: filter for subset of groups matching supplied keyword/phrase
          (boolean operators permitted)
      - in: query
        name: sort
        description: 'Sorts:* pid: sort alphabetically by PID'
      - in: query
        name: sort_direction
        description: Sort direction
      responses:
        200:
          description: OK
      tags:
      - Groups
  /images:
    get:
      summary: Find metadata for images
      description: Find metadata for images, particularly those in galleries
      operationId: listImages
      x-api-path-slug: images-get
      parameters:
      - in: query
        name: embargoed
        description: Control return of embargoed items (undocumented)
      - in: query
        name: group
        description: filter for images belonging to the given group (i
      - in: query
        name: image_type
        description: filter for images by type
      - in: query
        name: is_alternate_image_for
        description: filter for alternate images by entity PID
      - in: query
        name: is_image_for
        description: filter for images by entity PID
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: partner_id
        description: filter for images by partner ID
      - in: query
        name: partner_pid
        description: filter for images by partner PID
      - in: query
        name: pid
        description: filter for subset of images having given PID
      - in: query
        name: q
        description: filter for subset of images matching supplied keyword/phrase
          (boolean operators permitted)
      - in: query
        name: sort
        description: 'Sorts:* group_position: sort numerically by position, ascending
          only* pid: sort alphabetically by PID'
      - in: query
        name: sort_direction
        description: Sort direction
      responses:
        200:
          description: OK
      tags:
      - Images
  /items:
    get:
      summary: 'Look inside programmes to find segments: chapters, tracks and more'
      description: 'Look inside programmes to find segments: chapters, tracks and
        more'
      operationId: listItems
      x-api-path-slug: items-get
      parameters:
      - in: query
        name: authority
        description: filter for subset of items that have an ID issued by the given
          authority
      - in: query
        name: id
        description: filter for subset of items having given ID
      - in: query
        name: id_type
        description: filter for subset of items that have given an ID of the given
          type
      - in: query
        name: item_type
        description: filter for specific type(s) of items
      - in: query
        name: mixin
        description: 'Mixins:* contributions: mixin to return information about contributors
          to items* images: mixin to add image information for an item* offset: mixin
          to return programme segment offsets, works in conjunction with programme
          filter* play_event: mixin to return programme segment events, works in conjunction
          with programme or segment_event filters'
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: partner_id
        description: filter for items by partner ID
      - in: query
        name: partner_pid
        description: filter for items by partner PID
      - in: query
        name: people
        description: filter for subset of items that have specified person involved
      - in: query
        name: pid
        description: filter for subset of items matching one of the given PIDs
      - in: query
        name: programme
        description: filter for subset of items that are part of the given programme
      - in: query
        name: q
        description: filter for subset of items matching supplied keyword/phrase (boolean
          operators permitted)
      - in: query
        name: segment_event
        description: filter for item with the given segment_event
      - in: query
        name: sort
        description: 'Sorts:* pid: sort by pid, descending'
      - in: query
        name: sort_direction
        description: Sort direction
      responses:
        200:
          description: OK
      tags:
      - Items
  /master_brands:
    get:
      summary: List all Master Brands
      description: List all Master Brands
      operationId: listMasterbrands
      x-api-path-slug: master-brands-get
      parameters:
      - in: query
        name: mid
        description: filter for subset of masterbrands that have given identifier
      - in: query
        name: mixin
        description: 'Mixins:* images: mixin to add image information for a masterbrand'
      - in: query
        name: page
        description: which page of results to return
      - in: query
        name: page_size
        description: number of results in each page
      - in: query
        name: partner_id
        description: filter for masterbrands by partner ID
      - in: query
        name: partner_pid
        description: filter for masterbrands by partner PID
      - in: query
        name: q
        description: filter for subset of masterbrands matching supplied keyword/phrase
          (boolean operators permitted)
      - in: query
        name: sort
        description: 'Sorts:* mid: sort by mid, ascending'
      - in: query
        name: sort_direction
        description: Sort direction
      responses:
        200:
          description: OK
      tags:
      - Master
      - Brands
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