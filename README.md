# Wikidata filter

Used for WikiQA's MongoDB database (Wikidata) filtering 

## Requirements:
```
npm
nodejs
```

npm packages:

```
#wikidata-filter@3.0.2  it was buggy on simplifying claims and requires some dirty hacks, while the one below is less.
wikibase-dump-filter@5.0.5
load-balance-lines@1.0.5
```

## Installation

```
conda create -n wikidata-filter nodejs
conda activate wikidata-filter
npm install -g wikidata-filter@3.0.2
npm install -g load-balance-lines
```

wikidata-filter refs (This package has been renamed to wikibase-dump-filter by its author maxlath):
 - https://github.com/maxlath/wikibase-dump-filter
 - https://github.com/maxlath/wikibase-dump-filter/blob/master/docs/cli.md
 - https://www.npmjs.com/package/wikidata-filter
 - https://www.npmjs.com/package/wikibase-dump-filter
 
load-balance-lines:
 - https://github.com/maxlath/load-balance-lines

## Flow

Entities:
1. `wikidata-20191118-all.json` 847G
    - `sh get_wikidata_dump.sh`
2. `wikidata_entities_en_zh.json` and `wikidata_entities_zh_tw_cn_sim_richvalues_types.json` 70G
    - `sh run-wikidata-filter.sh`
3. `wikidata_properties.json` and `wikidata_properties_sim.json`
    - `sh run-wikidata-filter-properties.sh`
    
Note that the above scripts take quite a long time to finish.

## Output Files
`wikidata_entities_zh_tw_cn_sim_richvalues_types.json`
`wikidata_properties_sim.json`

