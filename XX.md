NIP-XX
======

NIP: XX
Title: Accommodation Rentals
Author: Patrick Geyer
Status: Draft
Type: Standards Track
Created: YYYY-MM-DD
---

## Abstract

This NIP defines `kind:30435` accommodation classifieds.
Extends the [NIP-99](99.md) classifieds NIP.

## Terms

- `guest` - NOSTR user that is searching for accommodation
- `host` - NOSTR user that is providing accommodation
- `listing` - item of accommodation


## Draft / Inactive Listings

`kind:30436` has the same structure as `kind:30435` and is used to save draft or inactive classified listings.

## Content

```
              title: 'Luxurious Villa with Ocean Views',
              description: "A luxurious villa with stunning ocean views...",
              price: [{amount: {value: 0.005, currency: Currency.BTC}, frequency: Frequency.daily}], // 0.005 per day
              minStay: Duration(days: 3), // 3 days min stay
              checkIn: TimeOfDay(hour: 16, minute: 0),
              checkOut: TimeOfDay(hour: 11, minute: 0),
              location: '101 Ocean Drive, Beach City',
              allowsBarter: bool,
              quantity: 1,
              images: [
                'https://a0.muscache.com/im/pictures/miso/Hosting-618573800623079625/original/2eecc731-6e8e-49c4-963a-2c9284c11900.jpeg?im_w=1200&im_format=avif',
                'https://a0.muscache.com/im/pictures/miso/Hosting-618573800623079625/original/3319ee8d-7f5f-4976-a936-cc74a7feb0c9.jpeg?im_w=720&im_format=avif',
                'https://a0.muscache.com/im/pictures/miso/Hosting-618573800623079625/original/ab1a5cdf-698f-4670-9088-1f2d08065f36.jpeg?im_w=720&im_format=avif',
                'https://a0.muscache.com/im/pictures/24c2d7ed-bf13-4050-aa3c-8dffd24b07e5.jpg?im_w=720&im_format=avif'
              ],
              type: ListingType.villa,
```

## Additional Tags

In addition to each tag appended as a standard NIP-99 listing, it should include the following tags when the value is not null or undefined.

```
List of amenities:
All default to zero or false if not specified or unparseable
```
{
    "airconditioning": boolean,
    "allows_pets": boolean,
    "bathtub": integer,
    "beds: integer,
    "tv": integer,
    "crib": boolean,
    "tumble_dryer": boolean,
    "washer": boolean,
    "elevator": boolean,
    "free_parking": boolean,
    "gym": boolean,
    "hair_dryer": boolean,
    "heating": boolean,
    "high_chair": boolean,
    "wireless_internet": boolean,
    "iron": boolean,
    "jacuzzi": boolean,
    "kitchen": boolean,
    "outlet_covers": boolean,
    "pool": boolean,
    "private_entrance": boolean,
    "smoking_allowed": boolean,
    "breakfast": boolean,
    "fireplace": boolean,
    "smoke_detector": boolean,
    "essentials": boolean,
    "shampoo": boolean,
    "infants_allowed": boolean,
    "children_allowed": boolean,
    "hangers": boolean,
    "flat_smooth_pathway_to_front_door": boolean,
    "grab_rails_in_shower_and_toilet": boolean,
    "oven": boolean,
    "bbq": boolean,
    "balcony": boolean,
    "patio": boolean,
    "dishwasher": boolean,
    "refrigerator": boolean,
    "garden_or_backyard": boolean,
    "microwave": boolean,
    "coffee_maker": boolean,
    "dishes_and_silverware": boolean,
    "stove": boolean,
    "fire_extinguisher": boolean,
    "carbon_monoxide_detector": boolean,
    "luggage_dropoff_allowed": boolean,
    "beach_essentials": boolean,
    "beachfront": boolean,
    "baby_monitor": boolean,
    "babysitter_recommendations": boolean,
    "childrens_books_and_toys": boolean,
    "game_console": boolean,
    "street_parking": boolean,
    "paid_parking": boolean,
    "hot_water": boolean,
    "lake_access": boolean,
    "single_level_home": boolean,
    "waterfront": boolean,
    "first_aid_kit": boolean,
    "handheld_shower_head": boolean,
    "home_step_free_access": boolean,
    "lock_on_bedroom_door": boolean,
    "mobile_hoist": boolean,
    "path_to_entrance_lit_at_night": boolean,
    "pool_hoist": boolean,
    "ev_charger": boolean,
    "rollin_shower",
    shower_chair,
    tub_with_shower_bench
    wide_clearance_to_bed
    wide_clearance_to_shower_and_toilet
    wide_hallway_clearance
    baby_bath
    changing_table
    room_darkening_shades
    stair_gates
    table_corner_guards
    extra_pillows_and_blankets
    ski_in_ski_out
    window_guards
    disabled_parking_spot
    grab_rails_in_toilet
    events_allowed
    common_spaces_shared
    bathroom_shared
    security_cameras
}

```
**Event Tags**:
```json
  "tags": [["d", <String, id of first issued event of this listing>]]
```

The a tag, used to refer to an addressable or replaceable event
for an addressable event: ["a", <kind integer>:<32-bytes lowercase hex of a pubkey>:<d tag value>, <recommended relay URL, optional>]