+++
title = "Survey"
hide_authorbox = true
[menu.main]
  weight = 4
+++

Please take a moment and tell me what you think about BluestNight.

{{< netlify-form name="bluestnight-survey" >}}
  {{< form-input type="text" label="First name:" id="first-name" placeholder="Richard" required="true" >}}
  {{< form-input type="text" label="Last name:" id="last-name" placeholder="Grayson" >}}
  {{< form-input type="email" label="Reply-to email:" id="email" placeholder="r.grayson@wayneindustries.com" >}}
  {{< mult-input type="radio" label="Do you use BluestNight on your website?" name="uses-theme" required="true" >}}
    {{< form-option label="Yes" value="yes" >}}
    {{< form-option label="No" value="no" selected="true" >}}
  {{< /mult-input >}}
  {{< form-input type="textarea" label="If yes, what has your experience been like?" id="dev-experience" >}}
  {{< mult-input type="radio" name="why-not-use" label="If no, why not?" add_other="true" >}}
    {{< form-option label="Not what I'm looking for" value="not looking for" >}}
    {{< form-option label="Too confusing to use" value="confusing" >}}
    {{< form-option label="I hadn't heard about it before" value="didn't know" >}}
  {{< /mult-input >}}
  {{< mult-input type="checkbox" name="theme-good-side" label="What, if anything, would you say BluestNight does well at?" add_other="true" >}}
    {{< form-option label="Plenty of customization" value="customization" >}}
    {{< form-option label="Detailed documentation" value="good docs" >}}
    {{< form-option label="Pages load quickly" value="fast load" >}}
    {{< form-option label="Developer friendly" value="dev-friendly" >}}
    {{< form-option label="Responsive design" value="responsive design" >}}
    {{< form-option label="Looks professional" value="looks professional" >}}
  {{< /mult-input >}}
  {{< form-input type="textarea" label="Explain:" id="good-theme-explanation" >}}
  {{< mult-input type="checkbox" name="theme-bad-side" label="What, if anything, should be improved in BluestNight?" add_other="true" >}}
    {{< form-option label="Site build time" value="build time" >}}
    {{< form-option label="Too many features" value="fewer features" >}}
    {{< form-option label="More approachable documentation" value="be approachable" >}}
    {{< form-option label="Too many bugs" value="has bugs" >}}
  {{< /mult-input >}}
  {{< form-input type="textarea" label="Explain:" id="bad-theme-explanation" >}}
  {{< form-input type="textarea" label="Is there anything else you would like to share?" id="anything-else" >}}
  {{< mult-input type="radio" label="If you entered an email above, may I contact you for follow-up information?" name="can-email" required="true" >}}
    {{< form-option label="Yes" value="yes" >}}
    {{< form-option label="No/Didn't enter email" value="no" selected="true" >}}
  {{< /mult-input >}}
{{< /netlify-form >}}
