# Draft issue: Flatpak extension for PTZ Controls

Paste the title and body below into a new issue on glikely/obs-ptz.

**Title:** Flatpak: package PTZ Controls as an OBS Studio extension?

---

Hi Grant,

I'd like to package obs-ptz for Flathub so Flatpak users of OBS Studio can
install it. I wanted to check with you before writing any code.

**How it works.** On Flathub an OBS plugin is not an app. It is an extension
named `com.obsproject.Studio.Plugin.<Name>`, installed into
`/app/plugins/<Name>`. The manifest normally lives in its own
`flathub/<id>` repo. The plugin repo can also keep a copy for CI and local
builds. Today `flatpak search obs-ptz` finds nothing, so there is no existing
package.

**Questions**

1. Do you want a Flatpak at all?
2. Who should maintain the `flathub/<id>` repo after the first submission:
   you, me, or both?
3. Which extension ID? I suggest `com.obsproject.Studio.Plugin.PTZControls`
   (the display name is "PTZ Camera Control for OBS").
4. How should we handle serial ports (VISCA/Pelco over serial)?
   - **A.** Build upstream `qtserialport` 6.11.1 in the manifest against OBS's Qt.
   - **B.** Add Linux support to the project's own copy, `shared/qtserialport`.
   - **C.** Ship the first version without serial support.
5. Should the manifest and a Flatpak CI job live in this repo?

I'm happy to do the packaging work. I just want to make sure it matches how
you'd like the project to be distributed.

Thanks!
