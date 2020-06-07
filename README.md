# geoindex
RTree-based spatial map.
Use whenever you have some spatial data you'd like assign some values to, then lookup those values later.

# use polygons as keys to retrieve data from the map

```rust
        use geo::polygon;

        let polygons = vec![polygon![
            (x: 0f32, y: 0f32),
            (x: 5f32, y: 5f32),
            (x: 5f32, y: 0f32),
        ]];
        let defs = vec![(polygons, 1)];

        let db = GeoIndex::new(defs, 0);

        assert_eq!(db.lookup_coords(Some(&Point::new(2f32, 1f32))), &1);
```
