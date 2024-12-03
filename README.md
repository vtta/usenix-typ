# usenix

This template is intended for submitting papers to USENIX conferences, include OSDI, NSDI, FAST, ATC, etc.

## Usage

You can use this template in the Typst web app by clicking "Start from template" on the dashboard and searching for `usenix`.

Alternatively, you can use the CLI to kick this project off using the command

```
typst init @preview/usenix
```



Typst will create a new directory with all the files needed to get you started.

## Configuration

This template exports the `ieee` function with the following named arguments:
- `title`: The paper's title as content
- `authors`: An array of author dictionaries. Each of the author dictionaries must have a `name`, and a `mark`.
- `affiliations`: An array of affiliation dictionaries. Each of the affliation dictionaries must have a `name`, and a `mark`.
- `review`: A boolean flag indicating whether we should hide content marked with `<anon>` to facilitate the anoymouse review process.
- `print`: A boolean flag indicating whether we should put links in a box for easier reading on screen.

The function also accepts a single, positional argument for the body of the paper.

The template will initialize your package with a sample call to the `usenix` function in a show rule. If you want to change an existing project to use this template, you can add a show rule like this at the top of your file:

```typ
#import "@preview/usenix:0.0.1": usenix

#let cuhk = image("logo-cuhk.svg", height: 0.6em)
#let typst = [#sym.dagger]

#show usenix.with(
  title: [
    A Typesetting System to Untangle the Scientific Writing Process
  ],
  authors: (
    (name: "Junliang Hu", email: "jlhu@cse.cuhk.edu.hk", mark: cuhk),
    (name: "Martin Haug", email: "haug@typst.app", mark: typst),
    (name: "Laurenz Mädje", email: "maedje@typst.app", mark: typst),
  ),
  affiliations: (
    (name: "The Chinese University of Hong Kong", mark: cuhk),
    (name: "Typst GmbH", mark: typst),
  ),
  review: true,
  print: true,
)

= Abstract
The process of scientific writing is often tangled up with the intricacies of typesetting, leading to frustration and wasted time for researchers. In this paper, we introduce Typst, a new typesetting system designed specifically for scientific writing. Typst untangles the typesetting process, allowing researchers to compose papers faster. In a series of experiments we demonstrate that Typst offers several advantages, including faster document creation, simplified syntax, and increased ease-of-use.


= Introduction
Scientific writing is a crucial part of the research process, allowing researchers to share their findings with the wider scientific community. However, the process of typesetting scientific documents can often be a frustrating and time-consuming affair, particularly when using outdated tools such as LaTeX. Despite being over 30 years old, it remains a popular choice for scientific writing due to its power and flexibility. However, it also comes with a steep learning curve, complex syntax, and long compile times, leading to frustration and despair for many researchers @netwok2020 @netwok2022.

== Paper overview
In this paper we introduce Typst, a new typesetting system designed to streamline the scientific writing process and provide researchers with a fast, efficient, and easy-to-use alternative to existing systems. Our goal is to shake up the status quo and offer researchers a better way to approach scientific writing.

By leveraging advanced algorithms and a user-friendly interface, Typst offers several advantages over existing typesetting systems, including faster document creation, simplified syntax, and increased ease-of-use.

To demonstrate the potential of Typst, we conducted a series of experiments comparing it to other popular typesetting systems, including LaTeX. Our findings suggest that Typst offers several benefits for scientific writing, particularly for novice users who may struggle with the complexities of LaTeX. Additionally, we demonstrate that Typst offers advanced features for experienced users, allowing for greater customization and flexibility in document creation.

Overall, we believe that Typst represents a significant step forward in the field of scientific writing and typesetting, providing researchers with a valuable tool to streamline their workflow and focus on what really matters: their research. In the following sections, we will introduce Typst in more detail and provide evidence for its superiority over other typesetting systems in a variety of scenarios.

= Methods <sec:methods>
#lorem(45)

$ a + b = gamma $ <eq:gamma>

#lorem(80)

#figure(
  placement: none,
  circle(radius: 15pt),
  caption: [A circle representing the Sun.]
) <fig:sun>

In @fig:sun you can see a common representation of the Sun, which is a star that is located at the center of the solar system.

#lorem(120)

#figure(
  caption: [The Planets of the Solar System and Their Average Distance from the Sun],
  placement: top,
  table(
    // Table styling is not mandated by the IEEE. Feel free to adjust these
    // settings and potentially move them into a set rule.
    columns: (6em, auto),
    align: (left, right),
    inset: (x: 8pt, y: 4pt),
    stroke: (x, y) => if y <= 1 { (top: 0.5pt) },
    fill: (x, y) => if y > 0 and calc.rem(y, 2) == 0  { rgb("#efefef") },

    table.header[Planet][Distance (million km)],
    [Mercury], [57.9],
    [Venus], [108.2],
    [Earth], [149.6],
    [Mars], [227.9],
    [Jupiter], [778.6],
    [Saturn], [1,433.5],
    [Uranus], [2,872.5],
    [Neptune], [4,495.1],
  )
) <tab:planets>

In @tab:planets, you see the planets of the solar system and their average distance from the Sun.
The distances were calculated with @eq:gamma that we presented in @sec:methods.

#lorem(240)

#lorem(240)

#bibliography("refs.bib", title: "References", style: "association-for-computing-machinery")

#set heading(numbering: "A.a.a")

= Artifact Appendix
In this section we show how to reproduce our findings.
```
