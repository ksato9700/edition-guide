<!--
# 2018-Specific Changes
-->
# 2018エディションに特有の変更

<!--
The following is a summary of changes that only apply to code compiled with
the 2018 edition compared to the 2015 edition.
-->
以下は、2015エディションにはなく、2018エディションでコンパイルされたコードにのみ適用される変更点のサマリです。

<!--
- [Path changes]:
    - Paths in `use` declarations work the same as other paths.
    - Paths starting with `::` must be followed with an external crate.
    - Paths in `pub(in path)` visibility modifiers must start with `crate`,
      `self`, or `super`.
- [Anonymous trait function parameters] are not allowed.
    - [Trait function parameters] may use any irrefutable pattern when the
      function has a body.
- Keyword changes:
    - [`dyn`] is a [strict keyword][strict], in 2015 it is a [weak keyword].
    - `async` and `await` are [strict keywords][strict].
    - `try` is a [reserved keyword].
- The following lints are now a hard error that you cannot silence:
    - [tyvar_behind_raw_pointer]
-->
- [パスの変更]
    - `use`宣言のパスは、他のパスと同様の働きをします
    - `::`で始まるパスは、次に外部クレート名がきます
    - アクセス修飾子`pub(in path)`のパスは、`crate`、`self`あるいは`super`から始まります
- [無名トレイト関数パラメータ]は許されません
    - [トレイト関数パラメータ]は、関数がボディを持つ場合に、論駁不可能なパターンを使うことがあります
- キーワードの変更
    - [`dyn`]は[厳格なキーワード][strict]です。2015エディションでは[弱いキーワード]でした
    - `async`と`await`は[厳格なキーワード][strict]です
    - `try`は[予約されたキーワード]です
- 以下の警告はコンパイルエラーになり、無視することはできなくなりました
    - [tyvar_behind_raw_pointer]

## Cargo
<!--
- If there is a target definition in a `Cargo.toml` manifest, it no longer
  automatically disables automatic discovery of other targets.
- Target paths of the form `src/{target_name}.rs` are no longer inferred for
  targets where the `path` field is not set.
- `cargo install` for the current directory is no longer allowed, you must
  specify `cargo install --path .` to install the current package.
  -->
- もし`Cargo.toml`マニフェストにターゲット定義があったとしても、自動のターゲットディスカバリーは有効です（訳注：2015エディションではターゲット定義があれば無効にされていました）
- `src/{target_name}.rs`という形にターゲットパスは、`path`フィールドが設定されていないターゲットであると推測しなくなりました。
- `cargo install`でカレントディレクトリのパッケージをインストールすることは許されなくなりました。それをしたい場合は、`cargo install --path .`と明示的に書く必要があります。

<!--
[Anonymous trait function parameters]: trait-system/no-anon-params.md
[Path changes]: module-system/path-clarity.md
[Trait function parameters]: https://doc.rust-lang.org/stable/reference/items/traits.html#parameter-patterns
[`dyn`]: trait-system/dyn-trait-for-trait-objects.md
[reserved keyword]: https://doc.rust-lang.org/reference/keywords.html#reserved-keywords
[strict]: https://doc.rust-lang.org/reference/keywords.html#strict-keywords
[tyvar_behind_raw_pointer]: https://github.com/rust-lang/rust/issues/46906
[weak keyword]: https://doc.rust-lang.org/reference/keywords.html#weak-keywords
-->
[無名トレイト関数パラメータ]: trait-system/no-anon-params.md
[パスの変更]: module-system/path-clarity.md
[トレイト関数パラメータ]: https://doc.rust-lang.org/stable/reference/items/traits.html#parameter-patterns
[`dyn`]: trait-system/dyn-trait-for-trait-objects.md
[予約されたキーワード]: https://doc.rust-lang.org/reference/keywords.html#reserved-keywords
[strict]: https://doc.rust-lang.org/reference/keywords.html#strict-keywords
[tyvar_behind_raw_pointer]: https://github.com/rust-lang/rust/issues/46906
[弱いキーワード]: https://doc.rust-lang.org/reference/keywords.html#weak-keywords
