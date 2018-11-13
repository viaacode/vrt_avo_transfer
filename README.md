# vrt_avo_transfer

Transfers files from the VRT tenant to the 'Archief voor Onderwijs' tenant.

## Synopsis

Mule API-backend for [vat.viaa.be](https://vat.viaa.be/).  It consists of:
- briefing_api: the backend for "vat",
- poller: checks the archival status for all items in the briefing that are not
  yet finished.

The web-interface for this application can be found here:
[vrt_avo_transfer_gui](https://github.com/viaacode/vrt_avo_transfer_gui).

## Examples

Some examples with [cURL](https://curl.haxx.se/).

### Validate briefing

**Request**

```shell
curl -H "Content-Type: application/json" \
	-d '{"briefing_id": "0a140e56-d00a-4bc8-84ee-f190353638e3"}'
	-X POST http://<host>:10002/briefings/validate
```

### Add briefing

**Request**

```shell
curl -H "Content-Type: application/json" \
	-d '<json below>'
	-X POST http://<host>:10002/briefings/validate
```

**JSON**

```json
{
    "data": {
        "briefing_id": "0a140e56-d00a-4bc8-84ee-f190353638e3",
        "briefing_titel": "Het weer & impact op mens, plant en dier & klimaat",
        "datum": "2018-08-20",
        "media_ids_audio": [],
        "media_ids_video": [
            {
                "media_id": "AIM00323133",
                "media_type": "video"
            }
        ],
        "uitvoerder": "Jane Doe",
        "viaa_pids": []
    },
    "status": "success"
}
```

