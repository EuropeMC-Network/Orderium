- Added support for `minecraft:custom_model_data` and `minecraft:dyed_color` components.
- Improved logging errors from NBT serializers
- Fixed an issue where choose item GUI always used sign GUI for search regardless of the config

### How to (components)
This is an example of using the `minecraft:custom_model_data` component in your item:

```yaml
id: minecraft:chest
count: 1
components:
  minecraft:custom_name: <!italic><aqua>Your Orders
  minecraft:lore:
  - <!italic><white>Click to view your orders
  minecraft:custom_model_data:
    floats: [4.0, 5.6, 99.1]
    strings: ["foo:bar"]
    colors: ["#03fcd7", "059fe7"]
```

The structures of the components are the same as vanilla.

However, **there are exceptions** for the color part.
`custom_model_data` has a list of colors and `dyed_color` has one color.
In vanilla, you can input a hex number, an integer or a list with 3 values (red, green, blue).

In Orderium, you cannot input an integer for the color, you can only input a hex string (without `0x` prefix), a hex string prefixed with `#`, a list of 3 values (like vanilla), and an object (a map) with 3 keys: red, green, and blue with values ranging from 0 to 255 (inclusive both ends).