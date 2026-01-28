

### LifeCycle Meta-Argument - Prevent Destroy

```sh

resource "local_file" "foo" {
  content  = "test"
  filename = "${path.module}/new_file"
  lifecycle {
    prevent_destroy = true
  }
}

```
```sh
Plan: 1 to add, 0 to change, 1 to destroy.
╷$ terraform apply
│ Error: Instance cannot be destroyed
│
│   on main.tf line 9:
│    9: resource "local_file" "foo" {
│
│ Resource local_file.foo has lifecycle.prevent_destroy set, but the plan calls for this resource to be destroyed. To avoid this error and continue    
│ with the plan, either disable lifecycle.prevent_destroy or reduce the scope of the plan using the -target option.
╵
```
