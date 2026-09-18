# FK POS

**Offline-first point-of-sale software for small businesses.**
8 industry-specific versions · 5 active businesses · Turkish market

→ [fkposyazilim.com](https://fkposyazilim.com)

> This is a showcase repository. FK POS is a commercial product, so the source code is not public — this page documents the architecture and the engineering decisions behind it.

---

## The problem

A shop cannot stop selling because the internet is down. Most modern POS software assumes a stable connection and degrades badly without one. FK POS is built the other way round: the register is the source of truth, and the cloud is an optional observer.

## Architecture

**Offline-first.** Sales, register operations, inventory and invoicing run entirely on the local machine. No connection is required for any part of the checkout flow.

**Cloud sync as an add-on.** An optional Supabase module pushes the current state of the register every 2 minutes, and immediately when connectivity returns, so the owner can watch the shop remotely while the till itself keeps working offline.

**Hardware in Rust.** Barcode scanners, electronic scales, thermal receipt printers and second customer displays are driven through Tauri commands in Rust, keeping device I/O out of the JavaScript layer.

**Encrypted single-file backups.** A custom .POS format packs the whole shop state into one encrypted file — simple enough for a shop owner to copy to a USB stick, safe enough to hand to support.

## Modules

Sales · Inventory · Accounts · Invoicing · Bulk price updates · Reporting

## Stack

React · TypeScript · Tauri · Rust · Supabase (PostgreSQL) · Windows

## My role

Everything: architecture, development, on-site installation at customer premises, and ongoing support.

---

Built and maintained by [Fırat Karataşoğlu](https://github.com/frat-karatasoglu).
