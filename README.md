# Google Cloud Service Extensions Samples

Recipes and code samples for
[Google Cloud Service Extensions](https://cloud.google.com/).

Each recipe has an example plugin written in Rust and C++, and an accompanying
unit test that verifies both.

# Samples & Recipes

The samples folder contains Samples & Recipes to use as a reference for your own
or extend them to fit your particular use case.

*   [Add HTTP request & response header](samples/add-http-header): Add an
    example header on both the client request and cdn response
*   [Overwrite HTTP request & response header](samples/add-http-header):
    Overwrite a particular header value from the client and from the origin with
    a new value

# Feature set / ABI

Service Extensions are compiled against the ProxyWasm ABI, described here:
https://github.com/proxy-wasm/spec/tree/master/abi-versions/vNEXT

Service Extensions currently support a subset of the ProxyWasm spec. Support
will grow over time. The current feature set includes:

*   Root context lifecycle callbacks
    *   on_vm_start
    *   on_configure
    *   on_done
    *   on_delete
*   Stream context lifecycle callbacks
    *   on_context_create
    *   on_done
    *   on_delete
*   Stream context HTTP callbacks
    *   on_request_headers
    *   on_response_headers
*   Stream context HTTP methods
    *   send_local_response
    *   get__header_map_value, add_header_map_value, replace_header_map_value,
        remove_header_map_value
    *   get_header_map_pairs, set_header_map_pairs
    *   get_header_map_size
*   Other methods
    *   log
    *   get_current_time_nanoseconds (frozen per stream)
    *   get_property ("plugin_root_id" only)
    *   get_buffer_status, get_buffer_bytes (PluginConfiguration only)

# TODO

*   API surface
    *   Publish and document the latest ProxyWasm version (not vNEXT as above)
*   Language support
    *   Add Golang recipes: https://github.com/tetratelabs/proxy-wasm-go-sdk

# License

All recipes and samples within this repository are provided under the
[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license. Please see
the [LICENSE](/LICENSE) file for more detailed terms and conditions.

# Code of Conduct

For our code of conduct, see [Code of Conduct](/docs/CODE_OF_CONDUCT.md).

# Contributing

Contributions welcome! See the [Contributing Guide](/docs/CONTRIBUTING.md).
