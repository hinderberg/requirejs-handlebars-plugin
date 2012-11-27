# RequireJS Handlebars Plugin

This plugin enables loading Handlebars templates dynamically during development and compile them during build.

## Usage

Define an template like `people.html`:

```handlebars
<div class="foo">
    <h1>{{title}}</h1>
    <ul>
        {{#each people}}
        <li>{{name}}</li>
        {{/each}}
    </ul>
</div>
```

Load it with the `hb` plugin:

```js
require(['hb!people'], function(people){
    var markup = people({
        title : 'A list of people',
        people : [
			{ name: 'hans' },
			{ name: 'kim' },
			{ name: 'mads' },
		]
    });
});
```

The plugins is only required for dynamic load so you can use the `r.js` setting `stubModules` to remove the `text!` and `hb!` plugins during build. And to remove unnecessary Handlebars code use `pragmasOnSave`and the `excludeHandlebars`.

## Example

Find example usage on: [Efficient JavaScript development in a Java world](https://github.com/kjbekkelund/js-java-setup)

## License

Released under the MIT license.

## Inspiration

This plugin is heavily inspired by the [RequireJS Hogan Plugin](https://github.com/millermedeiros/requirejs-hogan-plugin)
