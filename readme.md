# Example using the Constraint Validation API to add custom validations

Built-in validation for HTML forms is handled differently by the various browsers. But the underlying Contraint Validation API is well-supported and consistent and if necessary polyfills can extend support even further.

Custom validation can:

- make use of what browsers already offer to reduce code
- still add custom visual presentation
- trigger validation when needed
- easily add custom constraints and error messages

For an in-depth discussion see the 2017 [article series by Chris Ferdinandi on Constraint Validation](https://css-tricks.com/form-validation-part-1-constraint-validation-html/) where he builds a small validation library around this browser API.

_This example features:_

- an example function validate() to run validation, display error messages, and determine if the form as a whole is valid
- listen for form submits and trigger validate() first
- an example how to add a custom constraint which fakes a check to see if the entered username matches an imaginary existing username called "existingUsername"

## An opinion

I was surprised when I read the above mentioned articles and saw that there is a pretty solid basis. I still wonder why validation libraries reinvent the whole wheel instead of just adding single spokes. In the spirit of progressive enhancement it would make sense to add the common HTML validation attributes and a validation library picks them up instead of having to add library-specific syntax for common constraints like `required`. &mdash; Bootstrap makes use of the :valid and :invalid CSS pseudo-classes which use the Constraint Validation API. So if you don't need custom constraints, e.g. checking if a username exists, you could get validation and custom styling even with CSS only.

## Use

- focus the input field and hit the enter key to trigger the "required" contraint
- enter "existingUsername" and hit the enter key to see the custom constraint in action

## License

Licensed under the MIT license.
