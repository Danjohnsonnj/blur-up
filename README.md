# blur-up
Implementation exploration of blur-up progressive image loading. Inspired by <a href="https://css-tricks.com/the-blur-up-technique-for-loading-background-images/" target="blank">this</a> post at CSS-Tricks (which is an exploration of a <a href="https://code.facebook.com/posts/991252547593574/the-technology-behind-preview-photos/" target="blank">Facebook engineering team article</a>).

I explored taking an original high-quality image asset and converting it to a small thumbnail/placeholder image that would be displayed before the main content asset loads. This image will be a background image on the content image's parent wrapper (the placeholder is arguably decoration, not content, and should therefore be in the CSS). The content image will be using the `srcset` and `sizes` attributes (fallbacks are out of the scope of this exploration).

The placeholder image was created after testing various methods. The result is an image that is scaled down to 100px width at 72dpi, given a gaussian blur of 5px, then saved as a JPG at 50% quality, and finally run through <a href="https://imageoptim.com/" target="blank">ImageOptim</a>.

There are two versions of this example: one with the placeholder as an external image file, and another with the file base64-encoded and written into the wrapper as a background image. In both cases the remaining background-related styles are inline, as well, to avoid waiting for external CSS to be loaded and parsed.
