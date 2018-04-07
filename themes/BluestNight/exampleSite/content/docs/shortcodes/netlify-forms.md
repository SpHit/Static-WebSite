+++
title = "Netlify Forms"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
enable_toc = true
[menu.main]
  weight = 4
  parent = "docs-shortcodes"
+++

If you are using [Netlify](https://netlify.com) to host your Hugo site, BluestNight supports creating [Netlify-compatible](https://www.netlify.com/docs/form-handling/) forms in your content files through the use of a few shortcodes.

<!--more-->

Note that all parameters to these shortcodes are [named parameters](https://gohugo.io/templates/shortcode-templates/#positional-vs-named-parameters).

{{% alert %}}
This shortcode requires you to use the `{{</* shortcode */>}}` method of calling shortcodes. Using `{{%/* shortcode */%}}` instead will cause the form to render incorrectly.
{{% /alert %}}

# netlify-form

The `netlify-form` shortcode serves as a wrapper to the rest of the shortcodes on this page. Without it you may be able to use the other shortcodes to make form elements, but they won't submit anywhere. The other shortcodes are designed to be used as inner content to `netlify-form`.

**Required Parameters:**

- `name`: Equivalent to the [`name` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-name) on an HTML `<form>`. Must be unique among forms on the page.

**Optional Parameters:**

- `action`: The page to take the user to after they submit the form. Ideally should thank them for their submission. Defaults to a page from Netlify that redirects back to the page they left.

Example "Contact" form:

```
{{</* netlify-form name="contact" */>}}
  {{</* form-input id="firstname" type="text" placeholder="John" label="First Name:" required="true" */>}}
  {{</* form-input id="lastname" type="text" placeholder="Doe" label="Last Name:" */>}}
  {{</* form-input id="reply_email" type="email" placeholder="john.doe@email.com" label="Reply-To Email:" required="true" */>}}
  {{</* mult-input label="Gender:" name="gender" required="true" add_other="true" type="select" */>}}
    {{</* form-option label="Male" value="male" */>}}
    {{</* form-option label="Female" value="female" */>}}
  {{</* /mult-input */>}}
  {{</* form-input type="text" id="submit_reason" required="true" label="Reason for contacting:" placeholder="Problem with site" */>}}
  {{</* form-input id="contact_description" type="textarea" label="Explain:" required="true" */>}}
{{</* /netlify-form */>}}
```

# form-input

The `form-input` shortcode is used to create any form input except radio buttons and checkboxes, which are handled by [`mult-input`](#mult-input) instead. See [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_<input>_types) for a list of valid HTML `<input>` types.

BluestNight makes a few changes to the above list of input types for this shortcode. First, `textarea` is considered a valid input type, equivalent to the HTML `<textarea>` element, which is a multiline text entry field. Second, all "button" types are considered invalid, as the form automatically includes buttons to submit and clear the form. These invalid types are:

- `button`: A standard button
- `image`: A button made from an image
- `submit`: Submits the form
- `reset`: Clears the form, allowing the user to start over

If you enter an invalid input type, BluestNight will render a small warning where the input element should be.

Required parameters:

- `type`: A valid input type from the above link.
- `id`: A unique identifier for the input field. Must be unique across input elements in ***all*** forms on the page.
- `accept`: Only for `type="file"` inputs. Specify valid file types to submit. See [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-accept) for what valid values look like.

Optional parameters:

- `placeholder`: Placeholder text to appear inside the element as an example of valid input.
- `minlength`/`maxlength`: Set the minimum and/or maximum character length for the input.
- `regex`: A regular expression that valid input must match. Use types `email`, `url`, `date`, or `time` if you want to validate against one of those.
- `value`: Set a default value in the input field. Not recommended unless you have good reason.
- `required`: `"true"` if this input field is required.
- Numeric and Datetime inputs (`number`, `range`, `date`)
  - `min`: The minimum value allowed. [See more](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min).
  - `max`: The maximum value allowed. [See more](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max).
  - `step`: If specified, indicates that the value of the input must be equal to `min + n * step`, where n is an integer. [See more](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step).
- `file` and `email` type inputs
  - `multiple`: `"true"` if more than one file or email address can be entered in this field.

# mult-input

The `mult-input` shortcode acts as a wrapper around multiple *related* `radio` or `checkbox` elements.

Required parameters:

- `type`: `radio` or `select` for when only one selection can be made and `checkbox` for multiple selections.
- `name`: A unique identifier for the input field. Must be unique across input elements in ***all*** forms on the page.
- `label`: A label for the group of `radio` buttons or `checkboxes`

Optional parameters:

- `add_other`: `"true"` to add an "other" option to the end of the list with an accompanying textbox below it.
- `required`: For `radio` and `select` types. `"true"` if a selection is required.

# form-option

The `form-option` shortcode indicates one of a group of related options under a `mult-input`.

Required parameters:

- `label`: A label for this particular option.
- `value`: The value returned from the form when this option is selected. Is not displayed to the end user.

Optional parameters:

- `selected`: `"true"` for this option to be selected by default. Only add this to one option for `radio` and `select` types.
- `required`: `checkbox` only. `"true"` if *this* checkbox must be checked before the form is submitted. Do not use to indicate that at least one checkbox must be checked.
