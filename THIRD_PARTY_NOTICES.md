# Third-party notices

`oil-skills` is community repackaging maintained by larryboiNEUQ. It is not an official release of the upstream projects and does not claim inclusion in Anthropic's official plugin directory. The packaging adds marketplace metadata and documentation, not new skill functionality. Upstream skill text, scripts, resources, and retained relative paths are unchanged.

## oil-tone

- Source repository is https://github.com/oil-oil/oil-tone.
- Pinned commit is `39cbf92f76c90b7bb27a5b5d4ed88a1fc5fa31f6`.
- The complete tracked `skills/oil-tone/` tree is copied to `plugins/oil-suite/skills/oil-tone/`. The repository's root `LICENSE` is copied alongside it.
- License is MIT, copyright 2026 oil-oil. The preserved text is in [plugins/oil-suite/skills/oil-tone/LICENSE](plugins/oil-suite/skills/oil-tone/LICENSE).
- Files outside that tree are omitted, except the root `LICENSE`. The omitted tracked files are `.gitignore`, `README.md`, and `assets/readme/hero.svg`.

## oil-ui

- Source repository is https://github.com/oil-oil/oil-ui.
- Pinned commit is `1405c012bd4b435d051d8d1fd7f6ef616cae518a`.
- Tracked repository files are copied to `plugins/oil-suite/skills/oil-ui/`, except root `.gitignore` and `.github/workflows/`. This commit has no tracked workflows.
- License is MIT, copyright 2026 oil-oil. The preserved text is in [plugins/oil-suite/skills/oil-ui/LICENSE](plugins/oil-suite/skills/oil-ui/LICENSE).

The bundled Instrument Serif font has its own license. Copyright 2022 The Instrument Serif Project Authors, https://github.com/Instrument/instrument-serif. Its SIL Open Font License 1.1 is preserved in [assets/fonts/instrument-serif/OFL.txt](plugins/oil-suite/skills/oil-ui/assets/fonts/instrument-serif/OFL.txt), beside the unchanged font. The root MIT license does not relicense the font.

The bundled Alpine.js 3.17.4 file retains its upstream header, `Alpine.js 3.17.4 | MIT License | https://github.com/alpinejs/alpine`, in [assets/vendor/alpine.min.js](plugins/oil-suite/skills/oil-ui/assets/vendor/alpine.min.js). That file and its embedded notice are copied unchanged.

## oil-motion

- Source repository is https://github.com/oil-oil/oil-motion.
- Pinned commit is `07e31f2265f80caa8f2c1df825d85ac24a46307c`.
- Tracked repository files are copied to `plugins/oil-suite/skills/oil-motion/`, except root `.gitignore` and `.github/workflows/`.
- The excluded workflows are `.github/workflows/credential-ui.yml` and `.github/workflows/tests.yml`. No upstream workflow runs as part of this package's CI.
- License is MIT, copyright 2026 Lin Zhihuang. The preserved text is in [plugins/oil-suite/skills/oil-motion/LICENSE](plugins/oil-suite/skills/oil-motion/LICENSE).

## Packaging and provenance

The [root MIT license](LICENSE) preserves both upstream copyright holders and adds larryboiNEUQ for packaging. Each upstream license and embedded notice remains applicable to its files.

[provenance.json](provenance.json) records exact commits, copy roots, exclusions, and license mappings. Only tracked upstream files are selected. Git metadata and untracked runtime caches are not included. Retained README files, tests, resources, and configuration belong to the upstream snapshots and are not instructions to update a marketplace-managed copy outside the plugin update process.
