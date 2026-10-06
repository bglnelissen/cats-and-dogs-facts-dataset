# Cats and Dogs Facts Dataset

A merged and deduplicated dataset of 716 cat and dog facts (509 cats, 207 dogs) in JSON format, in English and in Dutch.

## Goal

This dataset is the data source for the [Cats and Dogs Facts HACS integration](https://github.com/bglnelissen/hacs-cats-and-dogs-facts) for Home Assistant. The integration shows a new fact every configurable number of hours.

## Files

| File | Language | Max length |
|------|----------|------------|
| `cats_and_dogs_facts.json` | English | 255 characters |
| `cats_and_dogs_facts.nl.json` | Dutch, plain language | 160 characters |

Cat and dog facts are mixed in one list.

### Structure

```json
{
  "meta": {
    "total": 716,
    "cats": 509,
    "dogs": 207,
    "sources": [...]
  },
  "facts": [
    "A cat has 32 muscles in each ear.",
    "..."
  ]
}
```

## Fact length

Home Assistant limits sensor state values to 255 characters. All 17 cat facts from the original sources that exceeded this limit have been manually rewritten, and the dog facts were shortened where needed. The core information of each fact is preserved.

The Dutch file is written for a small e-ink display, so every Dutch fact is at most 160 characters.

## Dog facts

The 431 unique dog facts from the source were edited down to 207: duplicates were merged, facts that were outdated or wrong were corrected or removed (for example, apple seeds contain a cyanide compound, not arsenic), and facts that are unsuitable for a family display were left out.

## Sources

| Source | License | URL |
|--------|---------|-----|
| alexwohlbruck/cat-facts (catfact.ninja) | Apache-2.0 | https://github.com/alexwohlbruck/cat-facts |
| vadimdemedes/cat-facts | MIT | https://github.com/vadimdemedes/cat-facts |
| wh-iterabb-it/meowfacts | MIT | https://github.com/wh-iterabb-it/meowfacts |
| DucNgn/Dog-Facts-API-v2 | MIT | https://github.com/DucNgn/Dog-Facts-API-v2 |
| kinduff/dog-api (original collection of the dog facts) | none stated | https://github.com/kinduff/dog-api |

## License

This dataset is released under the [MIT License](LICENSE).
