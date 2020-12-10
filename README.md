# image_magician-fix-for-php8
All GD functions that accepted resource values parameters prior to PHP 8.0 will now accept \GdImage objects.
Similarly, their return values will be \GdImage objects instead of resource. Validation against such values is now revised as followings.

if ( ! is_resource($this->imageResized) )
should be changed to:
if ( ! is_resource($this->imageResized) && !($this->imageResized instanceOf \GdImage) )
