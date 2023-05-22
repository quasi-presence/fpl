# Fantasy Points League (FPL)

## What is Fantasy Points League

Fantasy Points League is an application that will allow users to create, manage and participate in points based
fantasy leagues with family and friends.  Initial implementation is targeting support for a simple Nascar league
but could potentially expand into other motorsports, e-sports, etc...

## Project Design / Structure

A secondary purpose for Fantasy Points League is to serve as a test bed for exploring different technologies. To
best support that goal the project will consist of seperate frontend and backend implementations with separate
repositories.

The main feature list will be tracked in this repo and then each sub-project's README will list which features each
implementation supports, setup instuctions and misc notes.

See list of planned implementation repositories below.

While there maybe better libaries for specific stacks we'll be trying to select options that can be implemented across
several technology stacks (e.g. JWT for authentication, websockets, etc...).

## Models
  * RealLeague
    * id
    * name (e.g. Nascar, Supercross, etc...)
    * active
    * timestamps
  * RealSeason
    * id
    * real league
    * name
  * RealEvent
    * id
    * real season
    * name
    * date
  * RealCompetitor
    * id
    * name
  * RealResult
    * id
    * real event
    * real competitor
    * place
    * points
  * User
    * id
    * name - optional
    * email - required, unique
    * pwd - required
    * image_url
    * active
    * timestamps
  * UserLeague
    * id
    * owner
    * real league
    * name - required
    * image_url
    * active
    * timestamps
  * UserLeagueInvite
    * id
    * sender - required
    * recipient - required, unique
    * status - required
    * sent at - required
    * accepted at
    * timestamps
  * UserLeagueMember
    * id
    * fantasy league (required)
    * user (required)
    * name (required, unique per league)
    * timestamps
  * UserLeaguePick
    * id
    * fantasy league member
    * event - real event
    * pick - real competitor
    * order
    * place
    * points

## Repositories

* Application documentation - https://github/quasi-presence/fpl

* Frontends
  * Vue.js (tailwind) - https://github/quasi-presence/fpl-vue
  * Svelte - TBD
  * Tauri - TBD

* Backends
  * Rails (Ruby)- https://github/quasi-presence/fpl-rails
  * Flask (Python) - TBD
  * Warp (Rust) - TBD

## Features

  * [ ] Home page
  * [ ] Sign up
  * [ ] Login
  * [ ] Logout
  * [ ] View dashboard
  * [ ] View profile
  * [ ] Update profile
  * [ ] Create league
  * [ ] View dashboard/leagues
  * [ ] View league details
  * [ ] Invite league members
  * [ ] Create league event/schedule
  * [ ] Member notifications
    * [ ] Member picks
    * [ ] Event results
  * [ ] Select event picks
  * [ ] Enter event results
  * [ ] Collect real league data via APIs or web scrapers
    * [ ] Competitors
    * [ ] Scheduled events
    * [ ] Event results
  * [ ] TBD
