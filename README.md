# vote-inclusion-analyzer

**Checks for vote transactions by slot/account, with leader schedule and retry logic.**

**Note:**
_These RPC calls are very heavy. I've implemented extensive rate_limit handling to make this tool usable for everyone, but this can make the CLI slow and not ideal. Some queries may take a long time to complete. For best results, try to use a faster or less busy RPC endpoint. If a query appears stuck, please wait or try running the tool again, it will usually succeed eventually._

## Usage

```sh
vote-inclusion-analyzer --url https://api.mainnet-beta.solana.com \
                        --account GwHH8ciFhR8vejWCqmg8FWZUCNtubPY2esALvy5tBvji \
                        --slot 344883706 \
                        --distance 10
```

- `--url`      RPC endpoint (e.g. https://api.mainnet-beta.solana.com)
- `--account`  Vote account pubkey to filter for
- `--slot`     Starting slot number
- `--distance` How many slots back to check (inclusive)

## Dependencies

- Rust (2021 edition)
- [anyhow](https://crates.io/crates/anyhow)
- [clap](https://crates.io/crates/clap)
- [colored](https://crates.io/crates/colored)
- [reqwest](https://crates.io/crates/reqwest)
- [rand](https://crates.io/crates/rand)
- [serde](https://crates.io/crates/serde)
- [serde_json](https://crates.io/crates/serde_json)
- [solana-client](https://crates.io/crates/solana-client)
- [solana-program](https://crates.io/crates/solana-program)
- [indicatif](https://crates.io/crates/indicatif)
- [bs58](https://crates.io/crates/bs58)
- [bincode](https://crates.io/crates/bincode)

Build:

```sh
cargo build --release
```

## License

MIT

---
**No support. For professional/engineering use only. No responsibility for any damage =Q.Q=**
