# image-resizer@0.1.0

**Description**: Resize new images uploaded to a Cloud Storage bucket to a specified size. Both the original and the resized images are stored in the same bucket. Additionally, you can configure this mod to generate the signed URLs for both images and to store the URLs in Realtime Database.



**Configuration Parameters:**

* Deployment location: Where should the mod be deployed? You usually want a location close to your database. Realtime Database instances are located in us-central1. For help selecting a location, visit https://firebase.google.com/docs/functions/locations.

* Cloud Storage bucket for images: Which Cloud Storage bucket will contain the uploaded images that you want to resize? This bucket will also store the resized images.


* Maximum height of resized image: What do you want the maximum height of resized images to be (in pixels)? Learn more about how this mod resizes images to maintain aspect ratio in the mod's README.


* Maximum width of resized image: What do you want the maximum width of resized images to be (in pixels)? Learn more about how this mod resizes images to maintain aspect ratio in the mod's README.


* (Optional) Realtime Database path for signed URLs for images: What is the Realtime Database path where you want to store signed URLs for the original and resized images? Learn more about signed urls: https://cloud.google.com/storage/docs/access-control/signed-urls (or in this mod's README) If you prefer to not use signed URLs, leave this field empty.


* (Optional) Date after which signed URLs will expire (MM-DD-YYYY): After what date do you want the signed URLs to expire? Enter the date in MM-DD-YYYY format. If you prefer to not use signed URLs, leave this field as the default.


* (Optional) `cache-control` header for resized images: Do you want to specify a `cache-control` header for the resized image files? Learn more about `cache-control` headers: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control If you prefer not to use a `cache-control` header, leave this field empty.




**Mod Resources**

** * Cloud Functions:**

* **generateResizedImage:** (Listens for new images uploaded to your specified Cloud Storage bucket, resizes the images, then stores both images in the same Cloud Storage bucket.)



**APIs Used**:

* storage-component.googleapis.com (Reason: Needed to use Cloud Storage)



**Access Required**:



This mod will operate with the following project IAM roles:

* storage.admin (Reason: Allows the mod to store resized images in Cloud Storage)

* iam.serviceAccountTokenCreator (Reason: Allows the mod to generate signed URLs)

* firebasedatabase.admin (Reason: Allows the mod to store signed URLs in Realtime Database)
