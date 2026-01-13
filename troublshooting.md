# Screen Sharing on Teams and Edge

Using Wayland with Nvidia Drivers may freeze Fedora when sharing the screen. The possibilities of freezing reduce when Teams runs on Edge.

However, Edge sometimes crashes, and when it is restarted, it does not detect input and output sound devices. This happens because of a corrupted WirePlumber/PipeWire state. Run the following command on terminal to fix this:

``` rm -rf ~/.local/state/wireplumber ~/.config/wireplumber ~/.cache/pipewire ~/.local/state/pipewire systemctl --user restart pipewire pipewire-pulse wireplumber ```
