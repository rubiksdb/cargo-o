# what is cargo-o

  cargo-o is an object storage service and it is still under development.

# quick setup

  please be advised the the preview binaries are built on ubuntu-22.  other
  linux distribution may not work.

  download cargo-preview-11-2025.tgz from the repo, untar by
  ```
  tar xvf cargo-preview-11-2025.tgz
  cd wkk2
  ```

  start the service
  ```
  ./local/run-cargo.sh
  ```

  smoke test in a new terminal
  ```
  ./cargo/smoke-test.sh
  ```

# api spec

  find the the api spec under spec/cargo-api.yaml that is still envolving ...

# a few function highlights

  - sparse object support
  - parallel object IO (e.g multi-part upload)
  - bucket level snapshot

# key components

  ## wkk-libra

    root db that supports the block storage service

  ## wkk-cargo-be
  
    cargo backend service that offers both block storage service and object
    metadata database.

  ## cargo-api-service

    RESTFul api that offers bucket/object/io/snapshot operations as defined in
    the api spec.  It is built with openapi in Golang.
