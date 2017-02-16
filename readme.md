# Ivebe/Identitiles
Identitiles is yet another [identicon](https://en.wikipedia.org/wiki/Identicon) variant. For those who don't know, here is short description what identicon is:

> An Identicon is a visual representation of a hash value, usually of an IP address, that serves to identify a user of a computer system as a form of avatar while protecting the users privacy.

###### Why would I use it?
Identicons are widely used as a avatars that need to visually identify users which do not have personal avatar set. Something like the following sample for user comments.

<img width="594" alt="comment sample" src="https://cloud.githubusercontent.com/assets/4104576/23002960/d6eb078a-f3ed-11e6-9951-f13a398aba47.png">

### How does it work?
Identitiles use 32 byte MD5 hash to draw a 3x3 unique square. It's a simple JS library that will draw on a canvas, so no actual image will be stored on disk. Logic behind this is that we add one additional byte to the MD5 hash so that we have 33 bytes in total. First square use first 6 bytes for its color. Next 7 squares will use 3 bytes color, and last square will use 6 bytes color. Since color can only be represented as 3 or 6 bytes, we needed to add extra byte to the total 32 of MD5 hash.

### Usage
Pass MD5 hash into function which can be hash of IP address, email, username, or anything else that comes to your mind.

```html
<canvas id="canvas" width="90" height="90"></canvas>

<script src="identitiles.js"></script>
<script>
identitiles('canvas', '356ac8f205de4837377957243a5ed469');
</script>
```
