# OpenDRR Boundaries Database

## Workflow

(Draft, may be incomplete)

1. Download the compressed archive from @wkhchow
2. Extract the database file from the archive
3. Rename database dump to opendrr-boundaries-db.dump
4. Recompress with `7zz a -mx=9 -v2000m opendrr-boundaries-db.7z opendrr-boundaries-db.dump` to split into 2000 MiB volumes
5. Further split the files into 100 MiB chunks with `for i in *.7z.0??; do split -b 100M --verbose $i $i.; done`
6. `git add opendrr-boundaries-db.7z.001.??`
7. `git commit -S -m 'Update opendrr-boundaries-db.7z.001.?? // from opendrr-boundaries_with_full_hexgrid1km_remove_PT_aug2022.7z'`
8. `git push origin`
9. Repeat Steps 6–8 for opendrr-boundaries-db.7z.002.??, opendrr-boundaries-db.7z.003.??, etc.

## ChangeLog

### v1.4.4-alpha+20220621 (pushed 2022-07-29)

(previously tagged as `v1.4.4`)

* Original filename: `opendrr-boundaries_with_full_hexgrid1km_remove_PT.sql`
* File size: 8,729,712,573 bytes
* SHA-256 checksum: 7d773f69a9444e72b373a3b175a5be8f2812c69cb7043f5db6331b89210cb001
* Creation date: 2022-06-21
* From archive: `boundaries - update_900913.7z.001` – `boundaries - update_900913.7z.008`
