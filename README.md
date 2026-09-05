# Global IBAN, BIC/SWIFT & Bank Routing Validator API — Rust Client Crate

[![Crates.io](https://img.shields.io/crates/v/stanzaapi-iban-validator.svg)](https://crates.io/crates/stanzaapi-iban-validator)
[![Documentation](https://docs.rs/stanzaapi-iban-validator/badge.svg)](https://docs.rs/stanzaapi-iban-validator)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> ISO 13616 MOD-97 IBAN checksum verification, ISO 9362 BIC/SWIFT validation, and national bank routing extraction across 87 countries.

Official high-performance, asynchronous Rust client library for **Global IBAN, BIC/SWIFT & Bank Routing Validator API**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Uses pure Rustls TLS (zero C/OpenSSL dependencies) and Tokio for maximum concurrency and safety.

* 🌐 **Online Interactive Sandbox:** [Test your inputs live](https://stanzaapi.com/tools/iban-validator)
* 📚 **API Reference & Schemas:** [View documentation on Stanza](https://stanzaapi.com/tools/iban-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

Add to your `Cargo.toml`:

```toml
[dependencies]
stanzaapi-iban-validator = "1.0.0"
tokio = { version = "1.0", features = ["full"] }
```

Or use `cargo add`:

```bash
cargo add stanzaapi-iban-validator
```

---

## 🚀 Quickstart

```rust
use stanzaapi_iban_validator::IbanValidatorClient;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    // Reads STANZA_API_KEY from environment automatically
    let client = IbanValidatorClient::new(None, None);

    let response = client.validate("DE89370400440532013000").await?;

    if response.success {
        println!("Verification Success: {:?}", response.data);
    } else {
        eprintln!("Validation Error: {:?}", response.error);
    }

    Ok(())
}
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "iban": "DE89370400440532013000",
    "country_code": "DE",
    "bank_code": "37040044",
    "bic_candidate": "COBADEFFXXX"
  }
}
```

---

## 🔗 Useful Links

* [Global IBAN, BIC/SWIFT & Bank Routing Validator API Interactive Sandbox](https://stanzaapi.com/tools/iban-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/iban-validator-rust)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
