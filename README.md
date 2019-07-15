[![](https://jitpack.io/v/q42/androidscrollingimageview.svg)](https://jitpack.io/#q42/androidscrollingimageview)

# Scrolling Image View

An Android view for displaying repeated continuous side scrolling images. This can be used to create a parallax animation effect.

## Example

![Example](https://raw.githubusercontent.com/Q42/AndroidScrollingImageView/master/preview.gif)

## Installation

_Step 1._ Add the JitPack repository to your project `build.gradle` file

```gradle
allprojects {
    repositories {
        // ~~~
        maven { url 'https://jitpack.io' }
    }
}
```

_Step 2._ Add the dependency in the form

```gradle
dependencies {
    implementation 'com.github.satputekuldip:AndroidScrollingImageView:1.0.0'
}
```

## Sample app

Please see the sample app for some examples

![Sample App](https://raw.githubusercontent.com/Q42/AndroidScrollingImageView/master/sample_app.png)

## Usage

In your Android layout file add:

```xml
<com.spark.android.scrollingimageview.ScrollingImageView
    android:id="@+id/scrolling_background"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    scrolling_image_view:speed="1dp"
    scrolling_image_view:src="@drawable/scrolling_background" />
```

There are two attributes for the `ScrollingImageView` namely `speed` and `src`.

- `speed` is the number of `dp`'s to move the bitmap on each animation frame (may be a negative number)
- `src` is the drawable to paint (**must be a bitmap!**)

Don't forget to add the namespace to your root XLM element

```xml
xmlns:scrolling_image_view="http://schemas.android.com/apk/res-auto"
```

In your Java code, you can start and stop the animation like this:

```java
ScrollingImageView scrollingBackground = (ScrollingImageView) loader.findViewById(R.id.scrolling_background);
scrollingBackground.stop();
scrollingBackground.start();
```

## Parallax effect

In order to achieve a parallax effect, you can stack multiple `ScrollingImageView`'s in a `FrameLayout` with different speeds. For example:

```xml
<FrameLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

  <com.spark.android.scrollingimageview.ScrollingImageView
      android:id="@+id/scrolling_background"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      scrolling_image_view:speed="1dp"
      scrolling_image_view:src="@drawable/scrolling_background" />

  <com.spark.android.scrollingimageview.ScrollingImageView
      android:id="@+id/scrolling_foreground"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      scrolling_image_view:speed="2.5dp"
      scrolling_image_view:src="@drawable/scrolling_foreground" />
</FrameLayout>
```

## Originally Forked From

```html
<a href="https://github.com/Q42/AndroidScrollingImageView"
  >Q42/AndroidScrollingImageView</a
>
```

## License

```
Copyright 2019 Satpute Kuldip

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
