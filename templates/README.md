# Brevity is the soul of wit

and tediousness the limbs and outward flourishes, **you** will be brief.

---

Yes, I'm quoting [Hamlet](https://myshakespeare.com/hamlet/act-2-scene-2-popup-note-index-item-brevity-the-soul-of-wit#toggle-menu). 

And no, I don't mean irony. You **_will_** be brief and you **_must_** be brief.

**This repository is geared toward researchers looking to explore the possible datasets to use**. It describes each dataset in detail, so researchers don't have to find them all on their own. The datasets will be those which the majority of the industry and academic community are using, that are known to be reliable.

Think of it as buying a car. You'll need to study the specs carefully, maybe do a test drive before you decide to purchase it. If you have 100 cars in the market, ideally you'd want to study them all to decide which to buy.

Except you don't have that kind of time. You probably want to look at reviews, except those reviews are long-winded. You want a summary of all of those details which, at a glance, you can look at them and know what each one is about, what are the specs that are important.

You want more matter, with less art.

So. To contribute, please **write clearly and succinctly**. Understand what users want, and give it to them. The templates in this directory serve to provide some sort of structure you can follow, so you can **deliver high-level, dense, technical information quickly, without confusing the reader**. You don't need to follow them exactly, but they should act as a guide on how you can describe the data sources.

## Structure

Every directory should contain a `README.md` file for instructions and easier viewing. The structure of the `README` will vary depending on the level of the directory:

```
base repository (top-level)
├── category
│   ├── data source
│   │   └── dataset
```

#### `README` in top-level directory

should be about the repository (i.e. COVID-19). It should tell you what the repository is about, how to use the it, what are some resources that may complement the resources in this repository, that may be useful.

View the [template](top-level-readme-template.md) for top-level `README`.

#### `README` in each category

should define the category. It should have an index (table of contents) that tells you the high-level description of the datasets in the category, complete with additional relevant details such as comprehensiveness of data, and tags for easier classification.

For clarity, the `README` should also contain field descriptions and tag descriptions from the table. Additional resources may be provided here.

View the [template](category-readme-template.md) for category-level `README`.

#### `README` in each data source

should describe (non-exhaustively) what the data source is, how data is collected, what datasets are available, how to access each dataset, how to cite it, any data use agreement, the structure of each dataset, among other things. This is the crux of the repository, where users will derive the most value from. The majority of your work will be done here.

View the [template](data-source-readme-template.md) for data source-level `README`.

#### `README` in each dataset

should tell you what the dataset contains, and the structure of each. Some information may be repeated from the data source `README`. 

View the [template](dataset-readme-template.md) for dataset-level `README`.

## Writing Considerations

When writing the `README`, keep in mind the goal of providing high-level, dense, technical information in the quickest and easiet way possible. Understand common user behaviors when reading technical documentation, notably:

- Users will likely **not** read everything top-to-bottom, but will jump here and there, skim through sections to get to the information they want. Information should **jump out** at them. Users shouldn't have to go scrambling to find what they want. It is important, therefore, to use visual cues to grab their attention:
  - Use clear, simple structure, proper headings, subheadings
  - Important information should be **bolded**
  - Unfamiliar terms should be _italicized_
  - Use Markdown commands that will give correct semantics
  - Use **bulletted lists** instead of long paragraphs
  - Or long paragraphs, but **bold** the points
  - Try to provide as much visuals to reduce concentration effort
    
- Users don't want to open a new tab, or scroll back and forth and study new information they don't understand -- that takes too much effort
  - Provide links to useful resources where appropriate, **without having them find it themselves**
  - Repeat information in multiple places if necessary
  - Consider semantics and accessibility use cases outlined in [this article](https://www.smashingmagazine.com/2012/06/links-should-never-say-click-here/).

- Users don't want to waste time
  - Every word _counts_. Don't put it there if it serves nothing.
  - Use simple language that makes it effortless to understand the content
  - Leave out unimportant details. We want a high-level overview. Provide links to them instead.
  - Users should be able to understand everything at one quick glance, without re-reading
  
## Style Guide

I'm opinionated, so bear with me.

- Use headers to start a section. Don't bold a text to do it. i.e. use `## New section`, but don't do `**New section**`
- Leave a blank line before and after a header, a list, a code block, or whatever Markdown structure you're using
- Use `**bold**` for **bold**
- Use `_italics_` for _italics_
- Use `- list` for lists
- **Bullet heading**: bold it. And don't bold the `:`
- Style links with `[**title**](link)`, not `**[title](link)**`
- When a link is at the end of a sentence, put the period after the link, not inside of it. e.g. `[title](link).` not `[title.](link)`

Now for the more menial rules:

- Do not jump heading levels. e.g. Top-level heading is `#`, the sub-section from that should use `##`, not `###`. I break this rule sometimes 🤷‍♂️.
- End every sentence with a period (`.`)
- In bullet points though, don't end it with a period, **unless there is more than one sentence** ← (see, no period)
- You see. This point has many sentences. End it with a period. 
- In the event that you need to bold and italicize a word, italize before bold, aka `**_text_**` not `_**text**_`. This event should be rare, and ideally shouldn't happen at all.
- Follow the [quotation rules](https://www.grammarly.com/blog/quotation-marks/)
- Use the [Oxford comma](https://annhandley.com/oxford-comma/). Yes, do it.
- Use [reference-style links](https://www.markdownguide.org/basic-syntax/#reference-style-links) for repeated links
- Use three dashes `---` for a divider line

## Useful Resources
- [Markdown Guide](https://www.markdownguide.org/)
- [Markdown Table Generator](https://www.tablesgenerator.com/markdown_tables)
