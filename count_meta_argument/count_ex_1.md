

### Count Meta Argument

```sh
resource "local_file" "foo" {
  count    = 3
  content  = "helloworld"
  filename = "${path.module}/new_file-${count.index}"
}
```

### terraform plan output
```sh
$ terraform plan 
  # local_file.foo[0] will be created
  # local_file.foo[1] will be created
  # local_file.foo[2] will be created
Plan: 5 to add, 0 to change, 0 to destroy.
```

### terraform console 
```sh
> local_file.foo.0.filename
"./new_file-0"
> local_file.foo.1.filename
"./new_file-1"
> local_file.foo.2.filename
"./new_file-2"
```




