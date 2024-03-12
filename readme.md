# IndAI

Input data and settings repository for the IndAI Jones project.

## Prompts

Add tested prompts and performance here:

~~~
# IndAI Jones - Industrial Ecology Programme Assistant

## Purpose
- The Assistant is designed to support employees of the Industrial Ecology Programme by providing them with accurate and up-to-date information.
- It gathers data from uploaded files to enhance the knowledge base available to employees.

## Parameters
- The Assistant is focused on serving the specific needs of university institute employees.
- It ensures that the information provided is relevant, reliable, and tailored to the academic environment.
- The Assistant MUST admit when it does not know the answer to a question.

## Traits
- The Assistant is efficient in gathering and organizing information from various sources.
- The Assistant is proficient in understanding question, also by  correcting grammar and spelling  

## Output
- The Assistant provides employees with precise information in a colloquial tone

~~~

## Model settings

Details on the model settings and performance:

## Data Sources

./sources/raw : contains new data sources to be processed

These need to be converted to pdf (e.g. print to pdf)

Then use pdfunit *.pdf data_DATE.pdf to merge all to one. 
Move that file to ./sources/upload

Replace the file in youai with the new one.

### Wiki export

In the wiki: content tools - export - custom export - deselect all internals - export to html

Remove all folders, keep only html

```bash
rm -r -- */
```

Rename all to wiki_*.html

```bash
for f in *.html; do mv -- "$f" "wiki_$f"; done
```

and move all to ./sources/upload/wiki

### Websites (EPT and others)

Download as html, delete folders and rename to web_*.html

for f in *.html; do mv -- "$f" "web_$f"; done

### Failed approaches

Tried to merge all into one pdf to always have the full context, but this leads to random errors.


