---
title: URLhaus API
position_number: 1.6
type: post
description: URLhaus offers an API to both, receive (download) and submit malware URLs from the URLhaus database.
parameters:
  - name: url
    content: The URL you want to query URLhaus for
content_markdown: |-
  Beside the APIs documented on [URLhaus](https://urlhaus-api.abuse.ch/) that serves various feeds and lists, abuse.ch also offers a dedicated API that allows to gather information on a specific **URL**, **file hash** or **tag** from URLhaus through an automated way. It is also possible to retrieve a **payload** (malware sample) URLhaus has collected from malware URLs it tracks.
left_code_blocks:
  - code_block: |-
      $ Invoke-WebRequest -Uri 'https://urlhaus-api.abuse.ch/v1/url/' -Method POST -Body @{url='(url)'}
    title: Powershell
    language: bash
  - code_block: |-
      $ Invoke-WebRequest -Uri 'https://urlhaus-api.abuse.ch/v1/url/' -Method POST -Body @{url='http://sskymedia.com/VMYB-ht_JAQo-gi/INV/99401FORPO/20673114777/US/Outstanding-Invoices/'}
    title: Example
    language: bash
right_code_blocks:
  - code_block: |-
        {
          "query_status": "ok",
          "id": "105821",
          "urlhaus_reference": "https://urlhaus.abuse.ch/105821",
          "url": "http://sskymedia.com/VMYB-ht_JAQo-gi/INV/99401FORPO/20673114777/US/Outstanding-Invoices/",
          "url_status": "online",
          "hostname": "sskymedia.com",
          "date_added": "2019-01-19 01:33:26 UTC",
          "threat": "malware_download",
          "blacklist": {
            "spamhaus_dbl": "abused_legit_malware",
            "surbl": "listed",
          },
          "reporter": "Cryptolaemus1",
          "larted": true,
          "takedown_time_seconds": null,
          "tags": [
            "emotet",
            "epoch2",
            "heodo"
            ],
          "payloads": [
            {
              "firstseen": "2019-01-19",
              "filename": "5616769081079106.doc",
              "file_type": "doc",
              "response_size": "179664",
              "response_md5": "fedfa8ad9ee7846b88c5da79b32f6551",
              "response_sha256": "dc9f3b226bccb2f1fd4810cde541e5a10d59a1fe683f4a9462293b6ade8d8403",
              "urlhaus_download": "https://urlhaus.abuse.ch/v1/download/dc9f3b226bccb2f1fd4810cde541e5a10d59a1fe683f4a9462293b6ade8d8403/",
              "signature": null,
              "virustotal": {
                "result": "16 / 58",
                "percent": "27.59",
                "link": "https://www.virustotal.com/en/file/dc9f3b226bccb2f1fd4810cde541e5a10d59a1fe683f4a9462293b6ade8d8403/analysis/1547871259/"
              },
              "imphash": "4e4a95a7659118e966a42f4a73311fda",
              "ssdeep": "3072:+hcypCDJeA/9LH1sQx+YiSP2eiLe8/Gq2CeFUzJCfaDehYbAg9u/AJOOxxSEeXq1:LFZj1f+YiSP2Re8J2AehiQxOHSERtIgN",
              "tlsh": "1D340235A5E22807ED4F8479F75F8068BD4A8C96DE9DF244993C6A1A2077020C6F7F93"
            },
            {
              "firstseen": "2019-01-19",
              "filename": "ATT932454259403171471.doc",
              "file_type": "doc",
              "response_size": "174928",
              "response_md5": "12c8aec5766ac3e6f26f2505e2f4a8f2",
              "response_sha256": "01fa56184fcaa42b6ee1882787a34098c79898c182814774fd81dc18a6af0b00",
              "urlhaus_download": "https://urlhaus.abuse.ch/v1/download/01fa56184fcaa42b6ee1882787a34098c79898c182814774fd81dc18a6af0b00/",
              "signature": "Heodo",
              "virus_total": null,
              "imphash": "4e4a95a7659118e966a42f4a73311fda",
              "ssdeep": "3072:+hcypCDJeA/9LH1sQx+YiSP2eiLe8/Gq2CeFUzJCfaDehYbAg9u/AJOOxxSEeXq1:LFZj1f+YiSP2Re8J2AehiQxOHSERtIgN",
              "tlsh": "1D340235A5E22807ED4F8479F75F8068BD4A8C96DE9DF244993C6A1A2077020C6F7F93"
            }
          ]
        }
    title: Response
    language: json
---