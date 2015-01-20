selectize-placecomplete
=======================

plugin for [selectize](https://github.com/brianreavis/selectize.js), [see more](http://autoform-placecomplete.meteor.com) (demo with select2)

Usage
-----
```coffee
$("input[name='place']").selectize
  mode: "single"
  openOnFocus: false
  delimiter: null
  onInitialize: ->
    value = this.getValue()
    place_id = $("input[name='place_id']").val()
    this.updateOption value,
      value: value
      text: value
      description: value
      place_id: place_id
  plugins:
    'placecomplete':
      selectDetails: (placeResult) ->
        $("input[name='place_id']").val(placeResult.place_id)
        return null
```
