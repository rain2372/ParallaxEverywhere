# Parallax Everywhere #

Parallax everywhere (PEW) is a library with alternative android widgets with parallax effects.

## Demo ##

![](https://raw.githubusercontent.com/Narfss/ParallaxEverywhere/master/parallax-everywhere-animation-optimize.gif)

You can try the demo app on google play.

http://play.google.com/store/apps/details?id=com.fmsirvent.parallaxeverywhere

### Widgets with effect? ###

Android widget | PEW widget
--- | ---
ImageView | PEWImageView
TextView | PEWTextView

### How it works? ###

* Any parallax widget (PEW*) needs be inside a view with scroll events, ej: scrollView, listView, gridView....
* Parallax effect on widgets will be related to its position on device screen.
* Parallax effect in ImageView is calculate with left image in Scale mode centerCrop, centerInside or center. You can't make more parallax effect.
* Parallax effect in no image widgets needs a size parallax parameter (read:  Attributes)

### Show me the code ###

```
#!java

           <FrameLayout
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_gravity="center"
                android:layout_margin="10dp"
                android:layout_weight="1">

                <com.fmsirvent.ParallaxEverywhere.PEWImageView
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:layout_gravity="center"
                    android:layout_margin="10dp"
                    android:scaleType="centerCrop"
                    android:src="@drawable/alicante_explanada" />

                <com.fmsirvent.ParallaxEverywhere.PEWTextView
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:layout_margin="10dp"
                    android:gravity="bottom|center_horizontal"
                    android:text="@string/alicante_explanada"
                    android:textColor="@android:color/white"
                    pew:block_parallax_x="true"
                    pew:parallax_x="160dp"
                    pew:parallax_y="160dp"
                    pew:reverse="reverseY" />

            </FrameLayout>

```

### Attributes ###

**All PEW**

* **reverse**  = ["none", "reverseX", "reverseY", "reverseBoth"]
  Change animation direction of parallax effect. Default value "none".

* **block_parallax_x** and **block_parallax_y**  = "boolean"
  Blocks parallax effect. Default value false.

* **interpolation** = ["linear", "accelerate_decelerate", "accelerate", "anticipate", "anticipate_overshoot", "bounce", "decelerate", "overshoot"]
  Animation interpolation. Default value "linear".

**Only: no image PEW* **

* **parallax_x** and **parallax_y** = "dimension"
In non widgets images is necessary specify the size of parallax effect. The size will be split in half for each side. Default value 0.

## License

ParallaxEverywhere is available under the MIT license. See the LICENSE file for more info.
