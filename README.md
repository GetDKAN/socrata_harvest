## Socrata Harvest

This module will fill in required POD values where they are missing when harvesting from a Socrata data catalog.

## Install

```
composer require 'getdkan/socrata_harvest'
drush en socrata_harvest
```

## Harvest

Register the harvest, replace the **uri** value with the data.json url of your source:
```
drush dkan:harvest:register '{"identifier":"socrata","extract":{"type":"\\Harvest\\ETL\\Extract\\DataJson","uri":"https://YOUR-SOURCE/data.json"},"transforms":["\\Drupal\\socrata_harvest\\Harvest\\Transform\\Socrata", "\\Drupal\\harvest\\Transform\\ResourceImporter"],"load":{"type":"\\Drupal\\harvest\\Load\\Dataset"}}'
```

Run the harvest:
```
drush dkan:harvest:run socrata
```
