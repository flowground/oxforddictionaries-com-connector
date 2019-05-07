# ![LOGO](logo.png) Oxford Dictionaries **flow**ground Connector

## Description

A generated **flow**ground connector for the Oxford Dictionaries API (version 1.11.0).

Generated from: https://api.apis.guru/v2/specs/oxforddictionaries.com/1.11.0/swagger.json<br/>
Generated at: 2019-05-07T17:43:36+03:00

## API Description



## Authorization

This API does not require authorization.

## Actions

### Lists available domains in a bilingual dataset

> Returns a list of the available [domains](documentation/glossary?term=domain) for a given bilingual language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_domains_language` - _required_ - IANA language code
    Possible values: en, es, nso, zu, ur, de, pt.
* `target_domains_language` - _required_ - IANA language code
    Possible values: es, nso, zu, ms, id, tn, ro, de, pt.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available domains in a monolingual dataset

> Returns a list of the available [domains](documentation/glossary?term=domain) for a given monolingual language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_language` - _required_ - IANA language code
    Possible values: en, es, nso, zu, hi, sw, ur, de, pt, ta, gu.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve corpus sentences for a given word

> Use this to retrieve sentences extracted from  corpora which show how a word is used in the language. This is available for English and Spanish. For English, the sentences are linked to the correct [sense](documentation/glossary?term=sense) of the word in the dictionary. In Spanish, they are linked at the [headword](documentation/glossary?term=headword) level.<br/>
>   <div id="sentences"></div>

*Tags:* `The Sentence Dictionary`

#### Input Parameters
* `source_language` - _required_ - IANA language code
    Possible values: en, es.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve dictionary information for a given word

> Use this to retrieve definitions, [pronunciations](documentation/glossary?term=pronunciation), example sentences, [grammatical information](documentation/glossary?term=grammaticalfeatures) and [word origins](documentation/glossary?term=etymology). It only works for dictionary [headwords](documentation/glossary?term=headword), so you may need to use the [Lemmatron](documentation/glossary?term=lemma) first if your input is likely to be an [inflected](documentation/glossary?term=inflection) form (e.g., 'swimming'). This would return the linked [headword](documentation/glossary?term=headword) (e.g., 'swim') which you can then use in the Entries endpoint. Unless specified using a region filter, the default lookup will be the Oxford Dictionary of English (GB). <br/>
>   <div id="dictionary_entries"></div>

*Tags:* `Dictionary entries`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, lv, hi, sw, ta, gu.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve words that mean the opposite

> Retrieve words that are opposite in meaning to the input word ([antonym](documentation/glossary?term=thesaurus)).<br/>
> <br/>
>   <div id="antonyms"></div>

*Tags:* `Thesaurus`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Specify GB or US dictionary for English entry search

> USe this filter to restrict the lookup to either our Oxford Dictionary of English (GB) or New Oxford American Dictionary (US).

*Tags:* `Dictionary entries`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `region` - _required_ - Region filter parameter. gb = Oxford Dictionary of English. us = New Oxford American Dictionary.
    Possible values: gb, us.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve words that are similar

> Use this to retrieve words that are similar in meaning to the input word ([synonym](documentation/glossary?term=synonym)).<br/>
> <br/>
>   <div id="synonyms"></div>

*Tags:* `Thesaurus`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve synonyms and antonyms for a given word

> Retrieve available [synonyms](documentation/glossary?term=thesaurus) and [antonyms](documentation/glossary?term=thesaurus) for a given word and language. <br/>
> <br/>
>   <div id="synonyms_and_antonyms"></div>

*Tags:* `Thesaurus`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Apply filters to response

> Use filters to limit the [entry](documentation/glossary?term=entry) information that is returned. For example, you may only require definitions and not everything else, or just [pronunciations](documentation/glossary?term=pronunciation). The full list of filters can be retrieved from the filters Utility endpoint. You can also specify values within the filter using '='. For example 'grammaticalFeatures=singular'. Filters can also be combined using a semicolon.<br/>
> <br/>
>   <div id="dictionary_entries_filters"></div>

*Tags:* `Dictionary entries`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, lv, hi, sw, ta, gu.
* `word_id` - _required_ - An Entry identifier. Case-sensitive.
* `filters` - _required_ - Separate filtering conditions using a semicolon. Conditions take values grammaticalFeatures and/or lexicalCategory and are case-sensitive. To list multiple values in single condition divide them with comma.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve translation for a given word

> Use this to return translations for a given word. In the event that a word in the dataset does not have a direct translation, the response will be a [definition](documentation/glossary?term=entry) in the target language.<br/>
> <br/>
>   <div id="translation"></div>

*Tags:* `Translation`

#### Input Parameters
* `source_translation_language` - _required_ - IANA language code
    Possible values: en, es, nso, zu, ms, id, tn, ur, de, pt.
* `word_id` - _required_ - The source word
* `target_translation_language` - _required_ - IANA language code
    Possible values: es, nso, zu, ms, id, tn, ro, de, pt.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available filters

> Returns a list of all the valid filters to construct API calls.

*Tags:* `Utility`

#### Input Parameters
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available filters for specific endpoint

> Returns a list of all the valid filters for a given endpoint to construct API calls.

*Tags:* `Utility`

#### Input Parameters
* `endpoint` - _required_ - Name of the endpoint.
    Possible values: entries, inflections, translations.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available grammatical features in a dataset

> Returns a list of the available [grammatical features](documentation/glossary?term=grammaticalfeatures) for a given language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_language` - _required_ - IANA language code. If provided output will be filtered by sourceLanguage.
    Possible values: en, es, lv, nso, zu, ms, tn, ur, hi, sw, de, pt, ta, gu.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Check a word exists in the dictionary and retrieve its root form

> Use this to check if a word exists in the dictionary, or what 'root' form it links to (e.g., swimming > swim). The response tells you the possible [lemmas](documentation/glossary?term=lemma) for a given [inflected](documentation/glossary?term=inflection) word. This can then be combined with other endpoints to retrieve more information.<br/>
> <br/>
>   <div id="lemmatron"></div>

*Tags:* `Lemmatron`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, hi, nso, tn, zu, de, pt.
* `word_id` - _required_ - The input word
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Apply optional filters to Lemmatron response

> Retrieve available [lemmas](documentation/glossary?term=lemma) for a given [inflected](documentation/glossary?term=inflection) wordform. Filter results by categories.  <br/>
> <br/>
>   <div id="lemmatron_filters"></div>

*Tags:* `Lemmatron`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, hi, nso, tn, zu, de, pt.
* `word_id` - _required_ - The input word
* `filters` - _required_ - Separate filtering conditions using a semicolon. Conditions take values grammaticalFeatures and/or lexicalCategory and are case-sensitive. To list multiple values in single condition divide them with comma.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available dictionaries

> Returns a list of monolingual and bilingual language datasets available in the API

*Tags:* `Utility`

#### Input Parameters
* `sourceLanguage` - _optional_ - IANA language code. If provided output will be filtered by sourceLanguage.
    Possible values: es, en, lv, nso, zu, ms, id, tn, ur, hi, sw, ro, de, pt, ta, gu.
* `targetLanguage` - _optional_ - IANA language code. If provided output will be filtered by sourceLanguage.
    Possible values: es, en, lv, nso, zu, ms, id, tn, ur, hi, sw, ro.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available lexical categories in a dataset

> Returns a list of available [lexical categories](documentation/glossary?term=lexicalcategory) for a given language dataset.

*Tags:* `Utility`

#### Input Parameters
* `language` - _required_ - IANA language code
    Possible values: es, en, lv, nso, zu, ms, id, tn, ur, hi, sw, ro, de, pt, ta, gu.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available regions in a monolingual dataset

> Returns a list of the available [regions](documentation/glossary?term=regions) for a given monolingual language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_language` - _required_ - IANA language code
    Possible values: en.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available registers in a  monolingual dataset

> Returns a list of the available [registers](documentation/glossary?term=registers) for a given monolingual language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_language` - _required_ - IANA language code
    Possible values: en, es, hi, id, lv, ms, sw, ur, de, pt, ta, gu.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Lists available registers in a bilingual dataset

> Returns a list of the available [registers](documentation/glossary?term=registers) for a given bilingual language dataset.

*Tags:* `Utility`

#### Input Parameters
* `source_register_language` - _required_ - IANA language code
    Possible values: en, es, ms, id, ur, de, pt.
* `target_register_language` - _required_ - IANA language code
    Possible values: es, en, nso, zu, ms, id, tn, ro, de, pt.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve possible matches to input

> Use this to retrieve possible [headword](documentation/glossary?term=headword) matches for a given string of text. The results are culculated using headword matching, fuzzy matching, and [lemmatization](documentation/glossary?term=lemma) <br/>
> <br/>
>   <div id="search"></div>

*Tags:* `Search`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, hi, lv, sw, ta, gu.
* `q` - _optional_ - Search string
* `prefix` - _optional_ - Set prefix to true if you'd like to get results only starting with search string.
    Possible values: false, true.
* `regions` - _optional_ - If searching in English, filter words with specific region(s) either 'us' or 'gb'.
* `limit` - _optional_ - Limit the number of results per response. Default and maximum limit is 5000.
* `offset` - _optional_ - Offset the start number of the result.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve possible translation matches to input

> Use this to find matches in our translation dictionaries.<br/>
> <br/>
>   <div id="search_translation"></div>

*Tags:* `Search`

#### Input Parameters
* `source_search_language` - _required_ - IANA language code
    Possible values: en, es, nso, zu, ms, id, tn, ur, de, pt.
* `target_search_language` - _required_ - IANA language code
    Possible values: es, nso, zu, ms, id, tn, ro, de, pt.
* `q` - _optional_ - Search string.
* `prefix` - _optional_ - Set prefix to true if you'd like to get results only starting with search string.
    Possible values: false, true.
* `regions` - _optional_ - Filter words with specific region(s) E.g., regions=us. For now gb, us are available for en language.
* `limit` - _optional_ - Limit the number of results per response. Default and maximum limit is 5000.
* `offset` - _optional_ - Offset the start number of the result.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve the frequency of ngrams (1-4) derived from a corpus

> This endpoint returns frequencies of ngrams of size 1-4. That is the number of times a word (ngram size = 1) or words (ngram size > 1) appear in the corpus. Ngrams are case sensitive ("I AM" and "I am" will have different frequency) and frequencies are calculated per word (true case) so "the book" and "the books" are two different ngrams. The results can be filtered based on query parameters. <br> <br> Parameters can be provided in PATH, GET or POST (form or json). The parameters in PATH are overridden by parameters in GET, POST and json (in that order). In PATH, individual options are separated by semicolon and values are separated by commas (where multiple values can be used). <br> <br> Example for bigrams (ngram of size 2):<br/>
> * PATH: /tokens=a word,another word<br/>
> * GET: /?tokens=a word&tokens=another word<br/>
> * POST (json):<br/>
> <br/>
>   ```javascript<br/>
>     {<br/>
>         "tokens": ["a word", "another word"]<br/>
>     }<br/>
>   ```<br/>
> <br/>
> Either "tokens" or "contains" has to be provided. <br> <br> Some queries with "contains" or "sort" can exceed the 30s timeout, in which case the API will return an error message with status code 503. You mitigate this by providing additional restrictions such as "minFrequency" and "maxFrequency". <br> <br> You can use the parameters "offset" and "limit" to paginate through large result sets. For convenience, the HTTP header "Link" is set on the response to provide links to "first", "self", "next", "prev" and "last" pages of results (depending on the context). For example, if the result set contains 50 results and the parameter "limit" is set to 25, the Links header will contain an URL for the first 25 results and the next 25 results. <br> <br> Some libraries such as python's `requests` can parse the header automatically and offer a convenient way of iterating through the results. For example:<br/>
> ```python def get_all_results(url):<br/>
>     while url:<br/>
>         r = requests.get(url)<br/>
>         r.raise_for_status()<br/>
>         for item in r.json()['results']:<br/>
>           yield item<br/>
>         url = r.links.get('next', {}).get('url')<br/>
> ```

*Tags:* `LexiStats`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
* `corpus` - _required_ - For corpora other than 'nmc' (New Monitor Corpus) please contact api@oxforddictionaries.com
* `ngram-size` - _required_ - the size of ngrams requested (1-4)
* `tokens` - _optional_ - List of tokens to filter. The tokens are separated by spaces, the list items are separated by comma (e.g., for bigrams (n=2) tokens=this is,this was, this will)
* `contains` - _optional_ - Find ngrams containing the given token(s). Use comma or space as token separators; the order of tokens is irrelevant.
* `punctuation` - _optional_ - Flag specifying whether to lookup ngrams that include punctuation or not (possible values are "true" and "false"; default is "false")
* `format` - _optional_ - Option specifying whether tokens should be returned as a single string (option "google") or as a list of strings (option "oup")
* `minFrequency` - _optional_ - Restrict the query to entries with frequency of at least `minFrequency`
* `maxFrequency` - _optional_ - Restrict the query to entries with frequency of at most `maxFrequency`
* `minDocumentFrequency` - _optional_ - Restrict the query to entries that appear in at least `minDocumentFrequency` documents
* `maxDocumentFrequency` - _optional_ - Restrict the query to entries that appera in at most `maxDocumentFrequency` documents
* `collate` - _optional_ - collate the results by wordform, trueCase, lemma, lexicalCategory. Multiple values can be separated by commas (e.g., collate=trueCase,lemma,lexicalCategory).
* `sort` - _optional_ - sort the resulting list by wordform, trueCase, lemma, lexicalCategory, frequency, normalizedFrequency. Descending order is achieved by prepending the value with the minus sign ('-'). Multiple values can be separated by commas (e.g., sort=lexicalCategory,-frequency)
* `offset` - _optional_ - pagination - results offset
* `limit` - _optional_ - pagination - results limit
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve the frequency of a word derived from a corpus.

> This endpoint provides the frequency of a given word. When multiple database records match the query parameters, the returned frequency is the sum of the individual frequencies. For example, if the query parameters are lemma=test, the returned frequency will include the verb "test", the noun "test" and the adjective "test" in all forms (Test, tested, testing, etc.) <br> <br> If you are interested in the frequency of the word "test" but want to exclude other forms (e.g., tested) use the option trueCase=test. Normally, the word "test" will be spelt with a capital letter at the beginning of a sentence. The option trueCase will ignore this and it will count "Test" and "test" as the same token. If you are interested in frequencies of "Test" and "test", use the option wordform=test or wordform=Test. Note that trueCase is not just a lower case of the word as some words are genuinely spelt with a capital letter such as the word "press" in Oxford University Press. <br> <br> Parameters can be provided in PATH, GET or POST (form or json). The parameters in PATH are overriden by parameters in GET, POST and json (in that order). In PATH, individual options are separated by semicolon and values are separated by commas (where multiple values can be used). Examples:<br/>
> * PATH: /lemma=test;lexicalCategory=noun<br/>
> * GET: /?lemma=test&lexicalCategory=noun<br/>
> * POST (json):<br/>
> <br/>
>   ```javascript<br/>
>     {<br/>
>       "lemma": "test",<br/>
>       "lexicalCategory": "noun"<br/>
>     }<br/>
>   ```<br/>
> <br/>
> <br> One of the options wordform/trueCase/lemma/lexicalCategory has to be provided.

*Tags:* `LexiStats`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
* `corpus` - _optional_ - For corpora other than 'nmc' (New Monitor Corpus) please contact api@oxforddictionaries.com
* `wordform` - _optional_ - The written form of the word to look up (preserving case e.g., Books vs books)
* `trueCase` - _optional_ - The written form of the word to look up with normalised case (Books --> books)
* `lemma` - _optional_ - The lemma of the word to look up (e.g., Book, booked, books all have the lemma "book")
* `lexicalCategory` - _optional_ - The lexical category of the word(s) to look up (e.g., noun or verb)
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve a list of frequencies of a word/words derived from a corpus.

> This endpoint provides a list of frequencies for a given word or words. Unlike the /word/ endpoint, the results are split into the smallest units. <br> <br> To exclude a specific value, prepend it with the minus sign ('-'). For example, to get frequencies of the lemma 'happy' but exclude superlative forms (i.e., happiest) you could use options 'lemma=happy;grammaticalFeatures=-degreeType:superlative'. <br> <br> Parameters can be provided in PATH, GET or POST (form or json). The parameters in PATH are overridden by parameters in GET, POST and json (in that order). In PATH, individual options are separated by semicolon and values are separated by commas (where multiple values can be used). <br> <br> The parameters wordform/trueCase/lemma/lexicalCategory also exist in a plural form, taking a lists of items. Examples:<br/>
> * PATH: /wordforms=happy,happier,happiest<br/>
> * GET: /?wordforms=happy&wordforms=happier&wordforms=happiest<br/>
> * POST (json):<br/>
> ```javascript<br/>
>   {<br/>
>     "wordforms": ["happy", "happier", "happiest"]<br/>
>   }<br/>
> ```<br/>
> A mor complex example of retrieving frequencies of multiple lemmas:<br/>
> ```<br/>
>   {<br/>
>       "lemmas": ["happy", "content", "cheerful", "cheery", "merry", "joyful", "ecstatic"],<br/>
>       "grammaticalFeatures": {<br/>
>           "adjectiveFunctionType": "predicative"<br/>
>       },<br/>
>       "lexicalCategory": "adjective",<br/>
>       "sort": ["lemma", "-frequency"]<br/>
>   }<br/>
> ```<br/>
> Some queries with "collate" or "sort" can exceed the 30s timeout, in which case the API will return an error message with status code 503. You mitigate this by providing additional restrictions such as "minFrequency" and "maxFrequency". <br> <br> You can use the parameters "offset" and "limit" to paginate through large result sets. For convenience, the HTTP header "Link" is set on the response to provide links to "first", "self", "next", "prev" and "last" pages of results (depending on the context). For example, if the result set contains 50 results and the parameter "limit" is set to 25, the Links header will contain an URL for the first 25 results and the next 25 results. <br> <br> Some libraries such as python's `requests` can parse the header automatically and offer a convenient way of iterating through the results. For example:<br/>
> ```python def get_all_results(url):<br/>
>     while url:<br/>
>         r = requests.get(url)<br/>
>         r.raise_for_status()<br/>
>         for item in r.json()['results']:<br/>
>           yield item<br/>
>         url = r.links.get('next', {}).get('url')<br/>
> ```

*Tags:* `LexiStats`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
* `corpus` - _optional_ - For corpora other than 'nmc' (New Monitor Corpus) please contact api@oxforddictionaries.com
* `wordform` - _optional_ - The written form of the word to look up (preserving case e.g., Book vs book)
* `trueCase` - _optional_ - The written form of the word to look up with normalised case (Books --> books)
* `lemma` - _optional_ - The lemma of the word to look up (e.g., Book, booked, books all have the lemma "book")
* `lexicalCategory` - _optional_ - The lexical category of the word(s) to look up (e.g., adjective or noun)
* `grammaticalFeatures` - _optional_ - The grammatical features of the word(s) to look up entered as a list of k:v (e.g., degree_type:comparative)
* `sort` - _optional_ - sort the resulting list by wordform, trueCase, lemma, lexicalCategory, frequency, normalizedFrequency. Descending order is achieved by prepending the value with the minus sign ('-'). Multiple values can be separated by commas (e.g., sort=lexicalCategory,-frequency)
* `collate` - _optional_ - collate the results by wordform, trueCase, lemma, lexicalCategory. Multiple values can be separated by commas (e.g., collate=trueCase,lemma,lexicalCategory).
* `minFrequency` - _optional_ - Restrict the query to entries with frequency of at least `minFrequency`
* `maxFrequency` - _optional_ - Restrict the query to entries with frequency of at most `maxFrequency`
* `minNormalizedFrequency` - _optional_ - Restrict the query to entries with frequency of at least `minNormalizedFrequency`
* `maxNormalizedFrequency` - _optional_ - Restrict the query to entries with frequency of at most `maxNormalizedFrequency`
* `offset` - _optional_ - pagination - results offset
* `limit` - _optional_ - pagination - results limit
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve list of words for category with advanced options

> Use this to apply more complex filters to the [list of words](documentation/glossary?term=wordlist). For example, you may only want to filter out words for which all [senses](documentation/glossary?term=sense) match the filter, or only its 'prime sense'. You can also filter by word length or match by substring (prefix). <br/>
> <br/>
>   <div id="wordlist_advanced"></div>

*Tags:* `Wordlist`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, hi, lv, sw, ta, gu.
* `filters_advanced` - _required_ - Semicolon separated list of wordlist parameters, presented as value pairs: LexicalCategory, domains, regions, registers. Parameters can take comma separated list of values. E.g., lexicalCategory=noun,adjective;domains=sport. Number of values limited to 5.
* `exclude` - _optional_ - Semicolon separated list of parameters-value pairs (same as filters). Excludes headwords that have any senses in specified exclusion attributes (lexical categories, domains, etc.) from results.
* `exclude_senses` - _optional_ - Semicolon separated list of parameters-value pairs (same as filters). Excludes only those senses of a particular headword that match specified exclusion attributes (lexical categories, domains, etc.) from results but includes the headword if it has other permitted senses.
* `exclude_prime_senses` - _optional_ - Semicolon separated list of parameters-value pairs (same as filters). Excludes a headword only if the primary sense matches the specified exclusion attributes (registers, domains only).
* `word_length` - _optional_ - Parameter to speficy the minimum (>), exact or maximum (<) length of the words required. E.g., >5 - more than 5 chars; <4 - less than 4 chars; >5<10 - from 5 to 10 chars; 3 - exactly 3 chars.
* `prefix` - _optional_ - Filter words that start with prefix parameter
* `exact` - _optional_ - If exact=true wordlist returns a list of entries that exactly matches the search string. Otherwise wordlist lists entries that start with prefix string.
    Possible values: false, true.
* `limit` - _optional_ - Limit the number of results per response. Default and maximum limit is 5000.
* `offset` - _optional_ - Offset the start number of the result.
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

### Retrieve a list of words in a category

> Use this to retrieve a [list of words](documentation/glossary?term=wordlist) for particular [domain](documentation/glossary?term=domain), [lexical category](documentation/glossary?term=lexicalcategory), [register](documentation/glossary?term=registers) and/or [region](documentation/glossary?term=regions). View the full list of possible filters using the filters Utility endpoint.  The response only includes [headwords](documentation/glossary?term=headword), not all their possible [inflections](documentation/glossary?term=inflection). If you require a full [wordlist](documentation/glossary?term=wordlist) including [inflected forms](documentation/glossary?term=inflection), contact us and we can help.<br/>
> <br/>
>   <div id="wordlist"></div>

*Tags:* `Wordlist`

#### Input Parameters
* `source_lang` - _required_ - IANA language code
    Possible values: en, es, hi, lv, sw, ta, gu.
* `filters_basic` - _required_ - Semicolon separated list of wordlist parameters, presented as value pairs: LexicalCategory, domains, regions, registers. Parameters can take comma separated list of values. E.g., lexicalCategory=noun,adjective;domains=sport. Number of values limited to 5.
* `limit` - _optional_ - Limit the number of results per response. Default and maximum limit is 5000.
* `offset` - _optional_ - Offset the start number of the result
* `app_id` - _required_ - App ID Authentication Parameter
* `app_key` - _required_ - App Key Authentication Parameter

## License

**flow**ground :- Telekom iPaaS / oxforddictionaries-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
