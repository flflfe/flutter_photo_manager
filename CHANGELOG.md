# CHANGELOG

## 0.5.1-dev.2

Feature:

- Save image asset with file path.
- Copy asset to another album.
- Only iOS
  - Create folder or album.
  - Remove assets in album.
  - Delete folder or album.
  - Favorite asset.
- Only android
  - move asset to another path.
  - Remove all non-existing rows.

Fix:

- Problem of AssetPathEntity.refreshPathProperties.
- Open setting in iOS.

Change:

- Modified `AssetEntity.file`'s behavior on iOS, currently it will return a picture in jpg format instead of heic/gif/png. Now more in line with the description in the doc, this is suitable for uploading images (theoretically, no Exif information will be included).

## 0.5.0

Feature:

- Add `getSubPathEntities` for `AssetPathEntity`.
- Add `quality` for `AssetEntity.thumbDataWithSize`.
- Add `orientation` for `AssetEntity`.
- Add `onlyAll` for `getAssetPathList`.
- Support audio type(Only android, iOS Photos have no audio)
- **Breaking change**, Add date condition to filter datetime
  - Add class `DateTimeCond`
  - Add `dateTimeCond` to `FilterOptionGroup`
  - Remove `fetchDateTime` from `getAssetPathList`
  - Remove param `dt` from `AssetPathEntity.refreshPathProperties`, and add `refreshPathProperties` params to the method.

Update

- **Breaking change**, Split video filter and image filter
- iOS code is running background thread.
- getThumb is running in background thread.

Fix

- exists error on android.
- use edited origin file on iOS.
- galleryName maybe is null in android.
- thumb of android 10.

## 0.4.8

Fixes:

- [#169](https://github.com/CaiJingLong/flutter_photo_manager/issues/169)
- [#170](https://github.com/CaiJingLong/flutter_photo_manager/issues/170)

## 0.4.7

New feature:

- Add `FilterOption` for method `getAssetPathList`.

## 0.4.6

Fix:

- originFile of `AssetEntity`

Add:

- location(`latitude`,`longitude`) of `AssetEntity`
- `title` of `AssetEntity`
- `originBytes` of `AssetEntity`
- param `format` in `thumbDataWithSize` of assetEntity.

## 0.4.5

Fix:

- Can't get thumb/file of video on androidQ.

## 0.4.4

Fix:

- Compatibility code, when the width and height of the video is empty, it can still be scanned.
- Add a default value to `type` of `getAssetPathList`.

## 0.4.3

Add:

- Delete asset.
- Add Image.
- Add Video.
- Add modifiDate property.
- Fix videoDuration error.

Fix:

- CreateDate error.

## 0.4.2

- Fix ios get full file size error.

## 0.4.1

Fix:

- Fix ios build error.

## 0.4.0

Breaking change.

- Some properties in the entity were modified from asynchronous to synchronous.
- Remove `isCache` params. Now, `getAssetPathList` will reload info everytime. If user want to cache `List<AssetPathEntity>`, then user must do it self.

Added:

- Added a method `getAssetListPaged` for paging loading resources to path. The paging implementation is lazy loading, that is, the resource corresponding information is loaded when requested. The entity corresponding to the path is no longer placed in the memory, but is implemented by PHPhoto (ios) and sqlite's limit offset (android).
- Support AndroidQ privacy.

## 0.3.5

Fix

- ICloud image problem.

## 0.3.4

Support flutter 1.6.0 android's thread changes for channel.

## 0.3.3

Fix customizing album containing folders on iOS.

## 0.3.2

`AssetEntity` add property: `originFile`

## 0.3.1

`AssetEntity` add property: `exists`

## 0.3.0

- Support Android X.
- **Breaking change**. Migrate from the deprecated original Android Support Library to AndroidX. This shouldn't result in any functional changes, but it requires any Android apps using this plugin to also migrate if they're using the original support library.

fix NPE for image crash on android.

add a method to create `AssetEntity` with id

add `isCache` for method `getImageAsset`,`getVideoAsset` or `getAssetPathList`

add observer for photo change.

add field `createTime` for `AssetEntity`

## 0.2.1

add two method to load video / image

`getVideoAsset` `getImageAsset`

## 0.2.0

add asset size field

release cache method

## 0.1.10

fix

    when number of photo/video is 0, will crash

## 0.1.9

add video duration

## 0.1.8 sort asset by data

## 0.1.7 fix bug

fix bug: Android's latest picture won't be found

update gradle wrapper version.

update kotlin version

## 0.1.6

Fix Android to get pictures that are empty bug.

## 0.1.5

support ios icloud image and video

## 0.1.4 fix bug

update all path hasVideo property

## 0.1.3 add params

add a params to help user disable get video

## 0.1.2 fix bug

ios get video file is async

## 0.1.1 fix ios video

fix 'ios video full file is a jpg' problem

## 0.1.0 support video

support video in android.
and will change api from ImageXXXX to AssetXXXX

## 0.0.3 fix bug

update for the issue #1 (NPE when request other permission on android)

## 0.0.2 update readme

## 0.0.1

first version

api for photo
