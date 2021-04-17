# Toggle Mic Mute

This keyboard macro should toggle muting the OS's audio input device

Using advice from the following:
- https://apple.stackexchange.com/a/247183
- https://superuser.com/a/397770

## How to
1. Open Automator
2. Make a new `Quick Action`
3. Make sure it receives `no input` for `any application`
4. Select `Run Apple Script` and type in the following code:
    ```
    set inputVolume to input volume of (get volume settings)
    if inputVolume = 0 then
        set inputVolume to 100
    else
        set inputVolume to 0
    end if
    set volume input volume inputVolume
    ```
5. Save
6. Navigate to `System Preferences > Keyboard > Shortcuts > Services > [Name of the Quick Action you just saved]`
7. Enable it and add a key binding/shortcut for it by entering it
8. (As needed) Navigate to `System Preferences > Security > Privacy > Accessibility` and add `Automator` to be allowed
