# Quickstart client

This is the [SpacetimeDB](https://spacetimedb.com) quickstart chat sample
[taken from the SpacetimeDB SDK repo](https://github.com/clockworklabs/com.clockworklabs.spacetimedbsdk/tree/release/latest/examples~/quickstart-chat)
but converted standalone example that doesn't require forking the SDK source code or any Rust tooling.

The related getting-started tutorial can be found [here](https://spacetimedb.com/docs/modules/c-sharp/quickstart) (but
it will only explain how the server is built).

## TLDR for getting started with this sample

1. Install spacetime DB from [https://spacetimedb.com/install](https://spacetimedb.com/install).
2. install .NET 8 SDK
3. install WASI workload
   ```bash
   dotnet workload install wasi-experimental
   ```
4. start the SpacetimeDB server in a separate terminal
   ```bash
   spacetime start
   ```
5. publish the server code from this solution (run in solution dir):
   ```bash
   spacetime publish --project-path server quickstart-chat
   ```
6. Run one or more client instances

## Regenerating bindings

Regenerate the bindings when you changed code in the server project (run in the solution dir):

```bash
spacetime generate --lang csharp --out-dir client\module_bindings --project-path server
```