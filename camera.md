## Orthographic


### Bottom left
![Image of grid with bottom left x y axis](images/grid-ortho-2d-xy-bottom-left.png)
```rust
// Get screen width and height
let (width, height) = {
    let dim = world.read_resource::<ScreenDimensions>();
    (dim.width(), dim.height())
};
// Set the transform for the camera
// transform defaults are (x: 0, y: 0, z: 0)
let mut transform = Transform::default();
// Set the Z-axis to 10.0 which should be enough for most 2d games.
transform.set_z(10.0);
// Create the camera entity
world
    .create_entity()
    .with(transform)
    .with(Camera::from(Projection::orthographic(
        0.0,
        width,
        0.0,
        height,
    )))
    .build();
```