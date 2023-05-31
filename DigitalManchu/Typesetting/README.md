# Digital Text Orientation

Manchu text is written vertically and from left to right. This is unlike both East Asian scripts (vertical, right to left), arabic scripts (horizontal, right to left) and the mainstream latin scripts (horizontal, left to right). Right to left scripts are handled by special Unicode codepoints, and many platforms implement their own method of displaying scripts in the East Asian orientation. However, it is challenging to find support in digital software for the Manchu/Mongolian script. This page compiles methods for digital Manchu typography for a variety of platforms.

> _**Directionality.**_ The Mongolian script is written vertically from top to bottom in columns running from left to right. In modern contexts, words or phrases may be embedded in hor- izontal scripts. In such a case, the Mongolian text will be rotated ninety degrees counter- clockwise so that it reads from left to right.
>
> When rendering Mongolian text in a system that does not support vertical layout, the text should be laid out in horizontal lines running left to right. If such text is viewed sideways, the usual Mongolian column order appears reversed, but this orientation can be workable for short stretches of text. There are no bidirectional effects in such a layout because all text is horizontal left to right.

(_The Unicode® Standard: Version 15.0 – Core Specification_, chapter [13.5](/DigitalManchu/Unicode/Unicode-v15-ch13-Mongolian.pdf))

## On the web: HTML

CSS Styles that facilitate displaying Manchu texts (taken from Wikipedia):

```css
.manchu {
  font-family: "Mongolian Baiti", "Mongol Universal White",
    "Noto Sans Mongolian", "Abkai Xanyan", "Abkai Xanyan LA", "Abkai Xanyan VT",
    "Abkai Xanyan XX", "Abkai Xanyan SC", "Abkai Buleku", "Daicing White",
    "Oyun Gurban Ulus Tig", "Oyun Qagan Tig", "Oyun Garqag Tig",
    "Oyun Har_a Tig", "Oyun Scnin Tig", "Mongolian BT";　// Fallback Fonts
  -webkit-writing-mode: vertical-lr;
  -o-writing-mode: vertical-lr;
  -ms-writing-mode: tb-lr;
  writing-mode: tb-lr;
  writing-mode: vertical-lr;
  vertical-align: text-top; // text alignment
}
```

You can choose to keep Latin text upright using

```html
ᡥᡝᡵᡤᡝᠨ <span style="text-orientation: upright;">i</span> ᠮᠠᠨᠵᡠ
```

[Read more](https://www.w3.org/International/articles/vertical-text/index)

<details>
<summary>
Tricks for dealing with broken rendering on websites.
</summary>
If your browser usually renders Manchu/Mongolian script correctly, but fails for a particular website, inpecting the page and removing certain CSS styles might do the trick.
</details>

## Office Suites & Text Editors

Note: because the Manchu/Mongolian script is written left-to-right, you cannot simply rotate a horizontally typed document by ninety degrees to get the desired result: the orientations of the letters themselves will always contradict the orientation of the lines.

### LibreOffice (cross platform)

![](/DigitalTextOrientation/libreoffice_example.png)

1. First time only: go to Libreoffice Preferences window and navigate to `Language Settings > Languages` and tick the `Asian` languages checkbox. Then you can select a language on the right–any of them will work.<sup><a href="https://ask.libreoffice.org/t/text-orientation-vertical-asian/1279">[source]</a></sup>
2. Go to `Format > Page Style`.
3. Select the `Page` pane.
4. Set the text direction to `Left-to-right (Vertical)`.
5. Click `Apply` and `OK`.

![](/DigitalTextOrientation/libreoffice_page_settings.png)

Note: the arrow keys still act funky, but it is definitely a workable solution

### Microsoft Word (cross platform)

Microsoft supports East Asian vertical scripts through `Layout > Text Direction`. However, it does not support left-to-right. You would have to handle line wraps manually, which defeats the purpose. Hence, Word is not recommended.

### Pages (MacOS)

Same issue with Word. You can get the East Asian variety of vertical (right-to-left) orientation by clicking on the Document tab to get the the relevant pane, and then ticking `Vertical`. To do this, you must have an East Asian language (Chinese, Japanese, and/or Korean) selected as a preferred language on your computer. See [Apple support](https://support.apple.com/zh-sg/guide/pages/tanc8021e516/mac).

![](/DigitalTextOrientation/pages_setting_pane.png)
