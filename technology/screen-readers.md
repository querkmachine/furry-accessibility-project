---
section: Assistive technology
title: Screen readers
---

Screen readers are a software tool, often used by people who are [blind](/design/for-blindness) or have [low vision](/design/for-low-vision).

They work by reading text and information about the user interface to the user, usually when the element is focused. Elements may be focused using a [mouse](/technology/mouse), [keyboard](/technology/keyboard), [touch surface](/technology/touchscreen), [braille display](/technology/braille-displays), or automatically by the screen reader.

Screen reader users are more likely to use keyboard or touchscreen navigation than a mouse.

## Availability

Screen readers are included in all major operating systems, including: 

- [Narrator on Windows](https://support.microsoft.com/en-gb/windows/hear-text-read-aloud-with-narrator-040f16c1-4632-b64e-110a-da4a0ac56917)
- [TalkBack on Android](https://support.google.com/accessibility/android/answer/6283677)
- [VoiceOver on iOS](https://support.apple.com/en-gb/guide/iphone/iph3e2e415f/ios)
- [VoiceOver on macOS](https://support.apple.com/en-gb/guide/voiceover/welcome/mac)

A number of third-party screen readers also exist, the most popular of these being [JAWS (paid)](http://www.freedomscientific.com/Products/Blindness/JAWS) and [NVDA (free)](https://www.nvaccess.org/download/), both for Windows operating systems.

The functionality available differs depending on the screen reader. Narrator on Windows is considered to lack many features, and it is much more common for Windows users to use JAWS or NVDA instead.

## Specific considerations

### Provide text alternatives

Screen readers can only announce text, this means that images, videos, charts, and other multimedia will not be available to screen reader users unless a text alternative is provided. 

Alternate text should be descriptive of the image's content and purpose without being too extensive. Concentrate on describing the focal point of the image. If the image contains any text that isn't repeated in the body copy, this should also be included.

For images, alternative text must be provided using the `alt` attribute.

{% highlight html %}
<img src="fursuit-walk-47.jpg" alt="A person dressed as a blue and green cat dabs in the middle of a plaza.">
<img src="convention.jpg" alt="The front of a large, red brick hotel. A large banner reading 'Fursona Con 2025' hangs above the entrance.">
{% endhighlight %}

For videos, either closed captions or a transcript of the video will suffice. The transcript, or a link to the transcript, should be displayed in proximity to the video player.

For audio, a transcript of the audio should be provded. The transcript, or a link to the transcript, should be displayed in proximity to the audio player.

For charts and graphs, consider also providing the data in another form, such as a table. 

For other forms of multimedia (such as Flash or Java applets), you may have to use your best judgement on how best to provide an alternative to the content. If you're unable to provide an alternative, consider adding text explaining why.

### Make content understandable out of context

By default, most screen readers will read through a page linearly, in the order that content appears in the page's HTML.

However, many screen readers include tools to quickly jump around the document, so that users can quickly find what they're looking for. This includes jumping between:

- landmark regions; such as the navigation, main content area, and footer
- heading elements
- links
- form inputs and buttons

As a consequence of this, there is no guarantee that a user will actually have experienced your page in a linear fashion, or will have context of what surrounds certain elements. 

To aid these users, make sure that these elements have text or labels that are unique and clearly describe their purpose when read out of context. 

For example, links with the text "click here" or "read more" will not mean anything to a screen reader user, especially if there's more than one on the page. 

### Specify the content language

Because screen readers read content aloud, it is necessary for the screen reader to know what language content has been written in, so that the correct pronunciation can be used. 

This is achieved using the `lang` attribute, with a two-letter [ISO 639-1 language code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) as a value.

You can define the document's language by applying the attribute to the `html` element. For example, if the document is in English:

{% highlight html %}
<html lang="en">
{% endhighlight %}

If parts of a page appear in different language, the `lang` attribute can be applied to a wrapping element. This quote, for example, includes a French phrase:

{% highlight html %}
<p>Gazing at the wide blue sky is a <span lang="fr">joie de vivre</span>.</p>
{% endhighlight %}

Foreign language words that have been widely adopted into English, such as *café* and *kindergarten*, do not need to be marked up separately.

### Don't try to fix pronunciation issues

Screen readers will often mispronounce terms that they can't recognise, such as proper nouns or concatenated phrases, such as might appear in brand names or usernames (abitlikethis).

Generally in these situations, it is best not to try and work around the problem. Screen reader users tend to be familiar with the quirks of the software they are using, and prefer that you don't attempt to fix issues like these. 

Attempting to fix mispronunciations may also be detrimental to other users. For example, spelling a name phonetically may produce the correct pronunciation in a screen reader, but will now be spelled incorrectly for a braille reader.

### Don't overuse emojis and Unicode characters

Screen readers will usually try to understand and announce Unicode characters, including emoji. 

However, an overabundance of these will become tedious for a screen reader user to read, as they aren't recognised as whole words and each character will instead have their full Unicode name read out, one at a time. 

You can listen to [an example of this effect in VoiceOver](https://twitter.com/kentcdodds/status/1083073242330361856).

### Screen readers work differently with different browsers

As screen readers are separate applications to web browsers, the same screen reader will often announce slightly differently depending on the browser being used. 

This is because screen readers depend on the browser exposing information via the 'accessibility tree' and not all browsers do this the same way.

As a result, it's generally a good idea to test the same screen reader in multiple browsers, to ensure that all browsers return acceptable results. 

WebAIM's annual screen reader survey includes a list of [the most common browser—screen reader combinations](https://webaim.org/projects/screenreadersurvey9/#browsercombos) among their results.

## Testing

As screen readers are included with many operating systems, the easiest way to test if a page works with a screen reader is to close your eyes and use one!

Screen readers can be daunting to use at first, however they are usually quick to learn and easy to use once you're familiar with them. 

## Further reading

- [The ninth WebAIM Screen Reader User Survey (2021)](https://webaim.org/projects/screenreadersurvey9/)

### Videos

- [A video introduction to using VoiceOver on macOS](https://www.youtube.com/watch?v=5R-6WvAihms)
- [A video introduction to using NVDA on Windows](https://www.youtube.com/watch?v=Jao3s_CwdRU)
- [A video of an NVDA user navigating an accessible and an inaccessible webpage](https://www.youtube.com/watch?v=7Rs3YpsnfoI)
