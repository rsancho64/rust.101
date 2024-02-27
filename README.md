# rust 101

rust 101 @
    - Ubuntu 23.04
    - user shell: fish (/usr/bin/fish)

[recipe](https://www.digitalocean.com/community/tutorials/install-rust-on-ubuntu-linux)

[fix](https://forum.garudalinux.org/t/getting-rust-related-error-in-fish-konsole/10373):
(replacing contents of `~/.cargo/env` w `set --export PATH $HOME/.cargo/bin $PATH`)

```sh
#!/usr/bin/fish   # ***!!
#/bin/sh

set --export PATH $HOME/.cargo/bin $PATH  # ***!!
# rustup shell setup
# affix colons on either side of $PATH to simplify matching
# case ":${PATH}:" in
#     *:"$HOME/.cargo/bin":*)
#         ;;
#     *)
#         # Prepending path in case a system-installed rustc needs to be overridden
#         export PATH="$HOME/.cargo/bin:$PATH"
#         ;;
# esac
```

```sh
rustc --version # > rustc 1.76.0 (07dca489a 2024-02-04)
mkdir ./rustprojects
cd ./rustprojects
mkdir testdir
cd testdir
touch test.rs
```

```rs
fn main() {
    println!("Congratulations! Your Rust program works.");
}
```

```sh

ray@daw1 ~/E/r/r/testdir> rustc ./test.rs
ray@daw1 ~/E/r/r/testdir> ./test 
Congratulations! Your Rust program works.
```

## adenda: wez's term emulator (uses rust)

[install](https://wezfurlong.org/wezterm/install/linux.html) 

```sh
sudo apt install flatpak
flatpak install flathub org.wezfurlong.wezterm

Tenga en cuenta que las carpetas 

'/var/lib/flatpak/exports/share'
'/home/ray/.local/share/flatpak/exports/share'

no se encuentran en la ruta de búsqueda establecida por la variable de entorno
XDG_DATA_DIRS, por lo que es posible que las aplicaciones instaladas por
Flatpak no aparezcan en su escritorio hasta que se reinicie la sesión.
```

,, `flatpak run org.wezfurlong.wezterm` fails ; reset session: 

abandono. sigo con kitty

## - [ ] usos de rust
