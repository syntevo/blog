---
title: "Customizing the Graph colors for SmartGit 22.1"
date: "2022-10-30"
categories: 
  - "smartgit"
---

For SmartGit 22.1 we have extended the Graph color palette to 16 colors. Our main goal was to make collisions less likely. This has become an important objective as we have changed the overall Graph coloring logic to use constant, hash-based colors per branch. A drawback of the enlarged palette is that colors are not that distinctive anymore.

If you prefer to have different colors, you can use a custom theme file which just overrides _graph.connector.<number>_ values, then configure this file in Preferences, User Interface. For example, to have an almost identical palette as for version 21.x, you have to add one more color (e.g. red) and then duplicate these first 8 slots to slots 9-16:

graph.connector.1=derive(#80ff00, 0.7, 0.7)
graph.connector.2=derive(#0000ff, 0.6, 0.9)
graph.connector.3=derive(#ff8000, 0.6, 0.95)
graph.connector.4=derive(#c000c0, 0.5, 0.9)
graph.connector.5=derive(#0080ff, 0.7, 0.8)
graph.connector.6=derive(#ffff00, 0.8, 0.7)
graph.connector.7=derive(#00ff40, 0.8, 0.7)
graph.connector.8=derive(#ff0000, 0.8, 0.7)
graph.connector.9=derive(#80ff00, 0.7, 0.7)
graph.connector.10=derive(#0000ff, 0.6, 0.9)
graph.connector.11=derive(#ff8000, 0.6, 0.95)
graph.connector.12=derive(#c000c0, 0.5, 0.9)
graph.connector.13=derive(#0080ff, 0.7, 0.8)
graph.connector.14=derive(#ffff00, 0.8, 0.7)
graph.connector.15=derive(#00ff40, 0.8, 0.7)
graph.connector.16=derive(#ff0000, 0.8, 0.7)

A compressed theme file [graph-colors-v21.theme](https://www.syntevo.com/blog/wp-content/uploads/2022/10/graph-colors-v21.theme_.zip) with exactly this configuration is attached to this post, it just needs to be unpacked.

If you think to have found a nice palette for version 22.1, please share with us at [smartgit@syntevo.com](mailto:smartgit@syntevo.com).

For more details on custom themes, have a look at [Playing with themes](https://www.syntevo.com/blog/?p=4391).
