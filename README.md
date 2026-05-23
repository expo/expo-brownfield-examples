# media

This orphan branch hosts screenshot/recording assets for each per-repo brownfield integration.

Each `<NN>-<repo>/` directory contains:
- `recording.mp4` — short MP4 of the host app launching and the React Native screen rendering
- `poster.png` — still frame from the recording

Files are referenced from the per-repo Issue comments via
`https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/<NN>-<repo>/<file>`.

Don't merge this branch into `master`. It exists solely to keep media URLs stable without bloating the working tree.
