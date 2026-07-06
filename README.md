<!-- Language: **English** · [日本語](README.ja.md) · [繁體中文](README.zh-TW.md) -->
**English** · [日本語](README.ja.md) · [繁體中文](README.zh-TW.md)

# Shiomiwan Railway — Shiomi Line (汐見湾鉄道 汐見線)

A fictional route for BVE Trainsim 5 / 6. A 27.4 km, 12-station local
private railway that runs from a seaside town to a fog-wrapped hot-spring
resort — **ten different sceneries in a single ride**.

> Sea → Harbour → Coastline → City viaduct → Underground → Great truss bridge → Cherry-blossom avenue → Paddy fields → Satoyama → Gorge → Onsen town

## Line data

| Item | Value |
|------|-------|
| Section | Shiomihama – Kiriyama-Onsen |
| Operating distance | 27.4 km |
| Stations | 12 (4 with passing loops) |
| Gauge | 1,067 mm |
| Electrification | 1,500 V DC |
| Max speed | 95 km/h (65 km/h in mountains) |
| Steepest gradient | 33 ‰ (gorge section) |
| Min curve radius | R160 (gorge section) |
| Safety system | ATS-Sn (4-aspect automatic block, single track) |
| Run time | Local ≈ 42 min / Rapid ≈ 38 min |

## The ten scenery bands

| # | Section (km) | Scenery |
|---|--------------|---------|
| ① | 0.0–1.0 | Seaside city (terminus Shiomihama) |
| ② | 1.0–3.8 | Pacific coastline & lighthouse |
| ③ | 3.8–5.8 | Viaduct overlooking the city |
| ④ | 5.8–7.0 | Underground section & subway station |
| ⑤ | 7.0–8.5 | Truss bridge over the Okawa river |
| ⑥ | 8.5–12.5 | Cherry-blossom suburb |
| ⑦ | 12.5–16.5 | Open paddy fields |
| ⑧ | 16.5–20.0 | Satoyama cedar forest & shrine |
| ⑨ | 20.0–24.0 | Gorge (33 ‰, 5 tunnels, 3 steel bridges) |
| ⑩ | 24.0–27.4 | Fog-shrouded onsen town (terminus) |

## Bundled scenarios

| Scenario | Type | Weather | Notes |
|----------|------|---------|-------|
| `scenario/shiomi_day.txt` | Local (all-stop) | Day / clear | Standard, one-man operation |
| `scenario/shiomi_night.txt` | Local | Night | Moonlight & cab lamp only |
| `scenario/shiomi_rain.txt` | Local | Rain | Wet rail, prone to wheelslip — advanced |
| `scenario/shiomi_rapid.txt` | Rapid "Shiokaze" | Day / clear | Skips 5 stations, 38 min |

## Requirements

- BVE Trainsim 5.7 or later / BVE Trainsim 6
- Map format `BveTs Map 2.02`, encoding **UTF-8**

## Installation (tutorial)

> **Prerequisite:** BVE Trainsim is **Windows-only** (on macOS use Parallels /
> Boot Camp / a VM). If you don't have it yet, get it from the official site →
> [bvets.net download](https://bvets.net/en/download/)

### STEP 1 — Get the files
Use **Code → Download ZIP** at the top of this repo, or clone with Git:
```
git clone https://github.com/masonzeng702550/bve5-shiomi-line.git
```

### STEP 2 — Place it in your scenario folder
Put the whole `bve5-shiomi-line` folder under BVE's scenario folder, e.g.:
```
Documents\BveTs\Scenarios\bve5-shiomi-line\
```
In BVE, check **Options → Scenario** points to this folder. Do not change the
relative positions of `scenario\` and `Shiomi\` (all paths are relative).

### STEP 3 — Provide a train and edit the `Vehicle =` line
No train is bundled. Get any **commuter EMU (3-car recommended)** (see
"Getting a compatible train" below), then edit this line in each `.txt` under
`scenario\` to point at your train's `Vehicle.txt`:
```
Vehicle = ..\..\vehicle\generic_3car\vehicle.txt   ← change to your real path
```

### STEP 4 — Place the 3D models (.x) and textures
The right side of each line in `Shiomi\structure\structures.txt` is the path a
model should live at (e.g. `..\objects\coast\lighthouse.x`). Put the `.x`
models and `.png` textures at the matching `Shiomi\objects\...` locations.
To **test the alignment first without art assets**, comment out those lines by
prefixing `#`; you can then drive the whole route with track only.

### STEP 5 — Launch
Start BVE → on the scenario screen pick **"Shiomi Line Local for
Kiriyama-Onsen"** (night / rain / rapid appear too) → drive.

## Getting a compatible train (required separately)

Both local and rapid assume a **3-car** set (platform length, stop position
and timings are based on 3 cars), but any commuter EMU will work. Download a
free train below and swap it in per STEP 3. **Always check each distributor's
terms of use** before downloading.

| Source | Contents |
|--------|----------|
| [Official download (bvets.net)](https://bvets.net/en/download/) | Main program & official sample trains (Keisei Chiba Line, etc.) |
| [BVE5 vehicle data list (Players Wiki)](https://wikiwiki.jp/bvets/BVE5%E5%AF%BE%E5%BF%9C%E3%83%87%E3%83%BC%E3%82%BF%E4%B8%80%E8%A6%A7/%E8%BB%8A%E4%B8%A1%E3%83%87%E3%83%BC%E3%82%BF%E4%B8%80%E8%A6%A7%E8%A1%A8) | Comprehensive community index — see the "commuter / suburban EMU" section (easiest to browse) |
| [Tetsudo homepage](https://tetsudo-1998.jimdofree.com/bve5/%E8%BB%8A%E4%B8%A1%E3%83%87%E3%83%BC%E3%82%BF/) | Osaka Metro commuter trains (Midosuji 10 series, etc.; 7z) |
| [Chubu Shintoshi Unyu-ku](https://bvetk.arkw.net/download.html) | Vehicle & route data incl. commuter stock |
| [Yokohama Railway Lab](https://softwarenet.wixsite.com/yktrain/bve-data) | Distribution list incl. commuter stock |

> It doesn't have to be exactly 3 cars — longer sets still run, but may
> overrun the platform or stop off-mark.

## Troubleshooting

| Symptom | Cause | Fix |
|---------|-------|-----|
| Not shown in scenario list | Scenario folder not set | Re-check Options in STEP 2 |
| `File not found …\*.x` | 3D models not placed | STEP 4 (or comment the line out) |
| Won't start / vehicle error | Wrong `Vehicle =` path | Re-check the path in STEP 3 |
| Garbled text | Encoding | All files are UTF-8; open with a UTF-8 editor |

## Folder layout

```
scenario/                 Scenarios (day / night / rain / rapid)
Shiomi/
├── map/
│   ├── main*.txt         Map body per timetable (split with include)
│   ├── 00_init.txt       Global init
│   ├── 10..95_*.txt      Alignment & structures per scenery band
│   ├── signals.txt       Blocks, signals, ATS-Sn beacons
│   ├── trains.txt        Oncoming trains
│   └── env_night/rain.txt Night / rain environment overrides
├── station/              Station lists (local / rapid)
├── structure/            Structure list
├── signal/               Signal aspect list
├── sound/  sound3d/      Sound lists
└── objects/              3D models & textures (NOT included in this repo)
```

### Map design notes

- Split per scenery band with `include`; `main.txt` binds the load order.
- Night/rain reuse the day map unchanged: `env_night.txt` / `env_rain.txt` are
  **included last** to override lighting/background/fog at the same distances
  (no geometry or structures are duplicated).
- Rapid is achieved by swapping only the station list (`main_rapid.txt`).

## Assets

`Shiomi/objects/` ships **auto-generated placeholders** — a grey 1 m cube for
every model and 0.1 s of silence for every sound — so the route loads without
errors and can be driven end to end straight away (grey boxes for scenery).
Replace each `.x` / `.wav` with real models/audio to get the actual scenery;
follow the paths in the structure/sound lists. The train is still **not**
bundled (see STEP 3). See `Shiomi/objects/PLACEHOLDER.txt` and `CREDITS.txt`.

## Licence

Original work is under **CC BY-NC 4.0**. Third-party assets follow their
respective distributors' terms.

---

*This is a work of fiction. The line, company, station and place names are all imaginary.*
