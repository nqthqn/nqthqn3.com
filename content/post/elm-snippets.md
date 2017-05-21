+++
date = "2017-05-21T15:19:37-07:00"
title = "Elm snippets"

+++

## Mapping the View

This little piece of code takes a list and puts it into a grid of 4 x n.

```
List.map (div [ class "columns" ]) (List.map (\el -> div [ class "column" ] [ text el.content ]) stuff |> List.Extra.greedyGroupsOf 4)
```

So if `stuff` had 10 things in it that would produce:

```
<div class="columns">
    <div class="column">content</div>
    <div class="column">content</div>
    <div class="column">content</div>
    <div class="column">content</div>
</div>
<div class="columns">
    <div class="column">content</div>
    <div class="column">content</div>
    <div class="column">content</div>
    <div class="column">content</div>
</div>
<div class="columns">
    <div class="column">content</div>
    <div class="column">content</div>
</div>

```

## Updating a nested record

Apparently you can't do `{ model.nested | thing = 1 }`. You would have to do,

```
nested = 
    model.nested

nested_ =
    { nested | thing = 1 }

-- ...

{ model | nested = nested_ }
```

But you can write updater functions!

```
up_thing nested thing_ =
    { nested | thing = thing_ }

-- ...

{ model | nested = up_thing model.nested 1 }

```

So that's kind of nice. Nested records are not the best thing anyway. Probably because if you want to update one small deeply nested child you have to deal with all the parents, grandparents, inlaws, etc. ;). Not efficient, not fun. Keep it flat.

## Hard coded decoding

```
thingDecoder : JD.Decoder Thing
thingDecoder =
    JP.decode Thing
        |> JP.required "id" (JD.string)
        |> JP.required "content" (JD.string)
        |> JP.hardcoded False
```

That last line is kind of nice in case you need to do something awkward like this.

## Nested encoding

Sometimes your server might be expecting nested json. Here's an encoder for that:

```
thingEncoder : Thing -> JE.Value
thingEncoder t =
    JE.object
        [ ( "thing"
          , JE.object
                [ ( "id", JE.string t.id )
                , ( "content", JE.string t.content )
                , ( "booly", JE.bool t.booly )
                ]
            )
        ]
```

## Ports with no arguments

Sometimes you don't want to pass anything into a port.

```
port ping : () -> Cmd msg
```

Then in the update...

```
( model, Port.ping () )
```

And the js...

```
app.ports.ping.subscribe( function ( NOTHING ) {

    document.getElementById("ping").play()

})
```







