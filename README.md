# modal-slider-photos-and-videos

## Use for ionic 2

## Installation
```
npm i --save modal-slider-photos-and-videos
```

Config in the app.module.ts
```
import * as ionicGalleryModal from 'ionic-gallery-modal';
import { HAMMER_GESTURE_CONFIG } from '@angular/platform-browser';

imports: [
  //...
  ionicGalleryModal.GalleryModalModule,
  //...
],

providers: [
  //...
  {
    provide: HAMMER_GESTURE_CONFIG,
    useClass: ionicGalleryModal.GalleryModalHammerConfig,
  },
  //...
],
```

## Usage in the component
```
import { ModalController } from 'ionic-angular';
import { GalleryModal } from 'modal-slider-photos-and-videos';

constructor(
    //...
    public modalCtrl: ModalController,
    //...
){}
```

Slider photos:
```
let modal = this.modalCtrl.create(GalleryModal, {
  typeModal: "photo",
  photos: array_photo,
  initialSlide: currentIndex
});
modal.present();
```

Slider videos:
```
let modal = this.modalCtrl.create(GalleryModal, {
  typeModal: "video",
  videos: array_video,
  initialSlide: currentIndex
});
modal.present();
```


## Option
| Name | Type | Value | Description |
|------|------|-------|-------------|
| typeModal | string | "photo" | when use slider for photos |
| typeModal | string | "video" | when use slider for videos |
| photos | array | [] | is array information of all photos |
| videos | array | [] | is array information of all videos |
| initialSlide | number | 0 | pass params is index of a photo or a video need show |



#### Option of array photos
| Name | Type | Value | Description |
|------|------|-------|-------------|
| url | string |  | link of photo |
| avatar | string |  | link image avatar of user post this photo |
| name | string |  | name of user post this photo |
| title | string |  | title of this photo |
| date | string |  | date published this photo |

Example
```
{
  url: "http://example.com/images/photo_1.jpg",
  avatar: "http://example.com/avatar/david.jpg",
  name: "David Beckham",
  title: "Goal Goal!",
  date: "3 months ago"
}
```


#### Option of array videos
| Name | Type | Value | Description |
|------|------|-------|-------------|
| url | string |  | link local of video |
| poster | string |  | link of image show before play video |
| avatar | string |  | link image avatar of user post this video |
| name | string |  | name of user post this video |
| title | string |  | title of this video |
| date | string |  | date published this video |

Example
```
{
  url: "http://abc.com/media/video.mp4",
  poster: "http://example.com/poster/juventus.jpg",
  avatar: "http://example.com/avatar/buffon.jpg",
  name: "Buffon",
  title: "Save save!",
  date: "3 months ago"
}
```

