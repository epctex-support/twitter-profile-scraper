# Actor - Twitter Profile Scraper

Since Twitter doesn't provide a good and free API, this actor should help you to retrieve data from it.

## Features

-   Scrape user detail - Scrape any user related information from any profile such as friends, followers, following, verified account, location, profile image, profile banner, profile URL, date of creation and so on.

-   Scrape tweet - You can retrieve all the tweets from any profile with all the details. Language, sensitive language, reply, quote, retweet, pinned, retweeted and all sorts of Tweet related information.

- Scrape statistics - Gather all the statistical information of a tweet.

## Why using this actor?

This actor is extremely fast and optimized. It'll scrape Twitter proiles around 26 times faster than the other equivalent scrapers. Therefore you will consume less resources and it will be cheaper to use it.

## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/twitter-profile-scraper/issues).

## Input Parameters

The input of this scraper should be JSON containing the list of pages on Twitter Profile Scraper that should be visited. Possible fields are:

- `startUrls`: (Optional) (Array) List of Twitter Profile URLs. You should only provide profile URLs.

- `addUserInfo`: (Optional) (Boolean) This will add user information into all scraped tweets. Please keep in mind that the size of the output will increase proportionally by the user information.

- `onlyUserInfo`: (Optional) (Boolean)This option enables you to retrieve only user information and not the tweets of that user.

- `maxItems`: (Optional) (Number) You can limit scraped tweets. This should be useful when you scrape a profile with too many tweets.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to have a scrape over a specific profile URL, just copy and paste the link as one of the **startUrl**.

### Compute Unit Consumption

The actor optimized to run blazing fast and scrape many as tweets as possible. Therefore, it forefronts all tweet detail requests. If actor doesn't block very often it'll scrape 100 tweets in 20 seconds with ~0.02-0.025 compute units.

### Twitter Profile Scraper Input example

```json
{
  "proxy":{
    "useApifyProxy":true
  },
  "maxItems": 10,
  "addUserInfo":true,
  "startUrls":[
    "https://twitter.com/apify"
  ]
}

```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with failure state and output an explanation of what is wrong.

## Twitter Profile Scraper Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any languague (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Twitter Profile actor.

## Scraped Tweets Properties

The structure of each tweet in Twitter Profile Scraper looks like this:

### Tweet Detail

```json
{
  "user": {
    "created_at": "Tue Sep 01 08:38:01 +0000 2015",
    "default_profile": false,
    "default_profile_image": false,
    "description": "Apify is a software platform that lets you automate anything a person can do manually in a web browser, and then run it at scale.",
    "entities": {
      "description": {
        "urls": []
      },
      "url": {
        "urls": [
          {
            "display_url": "apify.com",
            "expanded_url": "https://apify.com",
            "url": "https://t.co/TmTF9tTQJv",
            "indices": [
              0,
              23
            ]
          }
        ]
      }
    },
    "fast_followers_count": 0,
    "favourites_count": 347,
    "followers_count": 1032,
    "friends_count": 164,
    "has_custom_timelines": false,
    "is_translator": false,
    "listed_count": 39,
    "location": "The Interweb",
    "media_count": 216,
    "name": "Apify",
    "normal_followers_count": 1032,
    "pinned_tweet_ids_str": [
      "1322257049527472128"
    ],
    "possibly_sensitive": false,
    "profile_banner_extensions": {
      "mediaColor": {
        "r": {
          "ok": {
            "palette": [
              {
                "percentage": 91.13,
                "rgb": {
                  "blue": 255,
                  "green": 249,
                  "red": 242
                }
              },
              {
                "percentage": 5.18,
                "rgb": {
                  "blue": 255,
                  "green": 188,
                  "red": 134
                }
              },
              {
                "percentage": 1.91,
                "rgb": {
                  "blue": 112,
                  "green": 110,
                  "red": 104
                }
              },
              {
                "percentage": 1.78,
                "rgb": {
                  "blue": 255,
                  "green": 157,
                  "red": 87
                }
              }
            ]
          }
        }
      }
    },
    "profile_banner_url": "https://pbs.twimg.com/profile_banners/3510729917/1602246779",
    "profile_image_extensions": {
      "mediaColor": {
        "r": {
          "ok": {
            "palette": [
              {
                "percentage": 86.89,
                "rgb": {
                  "blue": 255,
                  "green": 255,
                  "red": 255
                }
              },
              {
                "percentage": 4.83,
                "rgb": {
                  "blue": 19,
                  "green": 144,
                  "red": 255
                }
              },
              {
                "percentage": 4.27,
                "rgb": {
                  "blue": 1,
                  "green": 215,
                  "red": 150
                }
              },
              {
                "percentage": 3.05,
                "rgb": {
                  "blue": 233,
                  "green": 197,
                  "red": 113
                }
              },
              {
                "percentage": 0.29,
                "rgb": {
                  "blue": 169,
                  "green": 241,
                  "red": 221
                }
              }
            ]
          }
        }
      }
    },
    "profile_image_url_https": "https://pbs.twimg.com/profile_images/1354484488697425920/aQ5dSaTK_normal.jpg",
    "profile_interstitial_type": "",
    "protected": false,
    "screen_name": "apify",
    "statuses_count": 814,
    "translator_type": "none",
    "url": "https://t.co/TmTF9tTQJv",
    "verified": false,
    "withheld_in_countries": []
  },
  "created_at": "Thu Jul 14 13:34:06 +0000 2022",
  "conversation_id_str": "1547575166686793730",
  "display_text_range": [
    0,
    280
  ],
  "entities": {
    "media": [
      {
        "display_url": "pic.twitter.com/n5P2o3E7nG",
        "expanded_url": "https://twitter.com/apify/status/1547575166686793730/photo/1",
        "id_str": "1547575164660879363",
        "indices": [
          281,
          304
        ],
        "media_url_https": "https://pbs.twimg.com/media/FXoXabDUEAMR-4X.jpg",
        "type": "photo",
        "url": "https://t.co/n5P2o3E7nG",
        "features": {
          "large": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          },
          "medium": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          },
          "small": {
            "faces": [
              {
                "x": 272,
                "y": 39,
                "h": 36,
                "w": 36
              },
              {
                "x": 427,
                "y": 73,
                "h": 37,
                "w": 37
              }
            ]
          },
          "orig": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          }
        },
        "sizes": {
          "large": {
            "h": 640,
            "w": 1024,
            "resize": "fit"
          },
          "medium": {
            "h": 640,
            "w": 1024,
            "resize": "fit"
          },
          "small": {
            "h": 425,
            "w": 680,
            "resize": "fit"
          },
          "thumb": {
            "h": 150,
            "w": 150,
            "resize": "crop"
          }
        },
        "original_info": {
          "height": 640,
          "width": 1024,
          "focus_rects": [
            {
              "x": 0,
              "y": 0,
              "w": 1024,
              "h": 573
            },
            {
              "x": 0,
              "y": 0,
              "w": 640,
              "h": 640
            },
            {
              "x": 1,
              "y": 0,
              "w": 561,
              "h": 640
            },
            {
              "x": 121,
              "y": 0,
              "w": 320,
              "h": 640
            },
            {
              "x": 0,
              "y": 0,
              "w": 1024,
              "h": 640
            }
          ]
        }
      }
    ],
    "user_mentions": [],
    "urls": [
      {
        "display_url": "apify.it/3uKtuY5",
        "expanded_url": "https://apify.it/3uKtuY5",
        "url": "https://t.co/3l26ZicZjk",
        "indices": [
          257,
          280
        ]
      }
    ],
    "hashtags": [
      {
        "indices": [
          225,
          242
        ],
        "text": "instagramscraper"
      },
      {
        "indices": [
          243,
          255
        ],
        "text": "webscraping"
      }
    ],
    "symbols": []
  },
  "extended_entities": {
    "media": [
      {
        "display_url": "pic.twitter.com/n5P2o3E7nG",
        "expanded_url": "https://twitter.com/apify/status/1547575166686793730/photo/1",
        "ext_alt_text": "Three iPhone displays showing the description of three Instagram Scrapers from Apify Store: Instagram Profile Scraper, Instagram Hashtag Scraper, and Instagram Comment Scraper.",
        "id_str": "1547575164660879363",
        "indices": [
          281,
          304
        ],
        "media_key": "3_1547575164660879363",
        "media_url_https": "https://pbs.twimg.com/media/FXoXabDUEAMR-4X.jpg",
        "type": "photo",
        "url": "https://t.co/n5P2o3E7nG",
        "ext_media_color": {
          "palette": [
            {
              "percentage": 61.19,
              "rgb": {
                "blue": 242,
                "green": 242,
                "red": 242
              }
            },
            {
              "percentage": 18.76,
              "rgb": {
                "blue": 226,
                "green": 119,
                "red": 211
              }
            },
            {
              "percentage": 9.6,
              "rgb": {
                "blue": 189,
                "green": 120,
                "red": 147
              }
            },
            {
              "percentage": 3.7,
              "rgb": {
                "blue": 63,
                "green": 48,
                "red": 62
              }
            },
            {
              "percentage": 2.01,
              "rgb": {
                "blue": 195,
                "green": 120,
                "red": 228
              }
            }
          ]
        },
        "ext_media_availability": {
          "status": "Available"
        },
        "features": {
          "large": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          },
          "medium": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          },
          "small": {
            "faces": [
              {
                "x": 272,
                "y": 39,
                "h": 36,
                "w": 36
              },
              {
                "x": 427,
                "y": 73,
                "h": 37,
                "w": 37
              }
            ]
          },
          "orig": {
            "faces": [
              {
                "x": 411,
                "y": 60,
                "h": 55,
                "w": 55
              },
              {
                "x": 644,
                "y": 111,
                "h": 57,
                "w": 57
              }
            ]
          }
        },
        "sizes": {
          "large": {
            "h": 640,
            "w": 1024,
            "resize": "fit"
          },
          "medium": {
            "h": 640,
            "w": 1024,
            "resize": "fit"
          },
          "small": {
            "h": 425,
            "w": 680,
            "resize": "fit"
          },
          "thumb": {
            "h": 150,
            "w": 150,
            "resize": "crop"
          }
        },
        "original_info": {
          "height": 640,
          "width": 1024,
          "focus_rects": [
            {
              "x": 0,
              "y": 0,
              "w": 1024,
              "h": 573
            },
            {
              "x": 0,
              "y": 0,
              "w": 640,
              "h": 640
            },
            {
              "x": 1,
              "y": 0,
              "w": 561,
              "h": 640
            },
            {
              "x": 121,
              "y": 0,
              "w": 320,
              "h": 640
            },
            {
              "x": 0,
              "y": 0,
              "w": 1024,
              "h": 640
            }
          ]
        }
      }
    ]
  },
  "favorite_count": 0,
  "favorited": false,
  "full_text": "Extract profile information from Instagram with Instagram Profile Scraper! 📸 Quick, ready-made, and easy to set up, Instagram Scraper lets you extract usernames, followers &amp; follows, bio, likes, &amp; more. Try it now! 👇 #instagramscraper #webscraping  https://t.co/3l26ZicZjk https://t.co/n5P2o3E7nG",
  "is_quote_status": false,
  "lang": "en",
  "possibly_sensitive": false,
  "possibly_sensitive_editable": true,
  "quote_count": 0,
  "reply_count": 0,
  "retweet_count": 0,
  "retweeted": false,
  "source": "<a href=\"http://www.hubspot.com/\" rel=\"nofollow\">HubSpot</a>",
  "user_id_str": "3510729917",
  "id_str": "1547575166686793730"
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that is available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
