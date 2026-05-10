# Agent Living Off The Land (LOTL)

A set of agent skills helping agents to live off the land - that is, to operate without the need to search the internet or directly perform web requests, which often requires specific subscriptions or is blocked.

These skills teach agents techniques to make use of local dependency caches or CLIs which perform API queries to find up-to-date information about dependencies or language features. For example, using `terraform providers schema` to find the expected arguments of a resource in the installed version of a Terraform provider, or using `cargo doc` to locally generate documentation for the installed version of a Rust dependency.

