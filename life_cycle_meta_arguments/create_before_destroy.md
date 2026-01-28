

### LifeCycle Meta-Argument - Create Before Destroy

```sh
resource "local_file" "foo" {
  content  = "newdata"
  filename = "${path.module}/new_file"
  lifecycle {
    create_before_destroy = true
  }
}

```
```sh
local_file.foo: Creating...
local_file.foo: Creation complete after 0s [id=75941a16d5a6ada8e3d7f6facbebf4ab0c3a2ba4]
local_file.foo (deposed object e3701a19): Destroying... [id=a94a8fe5ccb19ba61c4c0873d391e987982fbbd3]
local_file.foo: Destruction complete after 0s
```
