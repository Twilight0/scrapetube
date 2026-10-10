# Changelog

## 2.8.3
- New `get_video_details(id, cookies)`: full `videoDetails` record (title,
  `shortDescription`, keywords, length, views, author, thumbnails,
  live/private flags) from `ytInitialPlayerResponse`, tolerant of both page
  layouts, with one retry on throttled stub pages.

## 2.8.2
- Import `Literal` from standard `typing` first, then `typing_extensions`,
  with a subscriptable fallback: fixes `type 'str' is not subscriptable` on
  minimal environments / Kodi Python.

## 2.8.1
- Tolerant continuation-token extraction in `get_next_data` (nested search,
  missing-token guard) instead of direct indexing.
- Playlist search (`results_type='playlist'`): parse current `lockupViewModel`
  playlist nodes (`LOCKUP_CONTENT_TYPE_PLAYLIST`, id in `contentId`) with
  title/thumbnail/channel enrichment.

## 2.8.0
- Merge of upstream fixes (`peoyli` + `ahai72160` lines) onto 2.6.0:
  `?view=2` channel URLs, `itemSectionRenderer` playlist container,
  `richItemRenderer`/`lockupViewModel`/`shortsLockupViewModel` parsers with
  dedup guard, `innertubeCommand` pagination fallback.
- `chipBarViewModel` + `showSheetCommand` sort filters (incl. membership
  channels), missing-filter tolerance.
- Channel-tab guard (existence + selected), richest-section playlist picker.
- Additive `title_text`/`is_live` fields; `title` keeps `runs` + `simpleText`
  shapes for backward compatibility.
- Optional login `cookies` on all calls with `SAPISIDHASH` continuation auth;
  logged-in `yt-initial-data` script-tag layout parsing.
- Clear errors when page data is missing instead of `JSONDecodeError`.

## 2.6.0
- Last upstream `dermasmid/scrapetube` release this fork builds on.
