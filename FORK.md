# Ercaner1988/turso — `yerel-0.8` dalı

Bu dal [tursodatabase/turso](https://github.com/tursodatabase/turso) `v0.8.2` etiketinin üstünde, upstream'den **yalnızca aşağıdaki farkları** taşır. Başka her şey upstream ile aynıdır; yeni sürüm çıktıkça bu dal upstream'in 0.8 hattına yeniden dayandırılır.

| Fark | Kaynak |
| --- | --- |
| `BTreeCursor::count`: iç sayfalarda sol-çocuk sayfa okuması iyileştirmesi + clippy düzeltmesi (2 commit) | upstream PR [tursodatabase/turso#8982](https://github.com/tursodatabase/turso/pull/8982) |
| `sync: order replayed schema operations per-transaction` birleştirmesi | upstream `v0.8` dalından (`124803b07`), sürüm artırımı olmadan |

Sürüm `0.8.2` kalır; böylece `turso = "0.8"` isteği `[patch.crates-io]` ile bu dala yönlendirilebilir.

## Neden `main` değil

Upstream `main`, bilinmeyen sanal tablo modülü olan veritabanını açmayı reddeder (`961870073`, 28 Eylül 2026); `fts5` tablosu içeren eski SQLite dosyaları bu yüzden açılmaz. 0.8 hattı bunu yalnızca uyarı olarak yazar.

## Kullanım

```toml
# .cargo/config.toml
[patch.crates-io]
turso = { git = "https://github.com/Ercaner1988/turso", branch = "yerel-0.8" }
```

## Upstream'i izleme

`main` dalı upstream `main` ile aynı tutulur; bu dosyadaki fark yalnızca `yerel-0.8` dalındadır.
