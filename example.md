:::mermaid
    mindmap [central node name]
        [title A title]
        [?parent]-->[name] [position] [bg-color] [text-color]
        -->mindmap-notation:right white black
        mindmap-notation-->has
        has-->position
        has-->bg-color
        has-->text-color
        position-->positions
        positions-->top
        positions-->bottom
        positions-->left
        positions-->right
        positions-->top-left
        positions-->top-right
        positions-->bottom-left
        positions-->bottom-right
        -->implementation:bottom blue
        implementation-->d3 is hard:red white
        -->backlog
        backlog-->TODO:yellow
        backlog-->notation to set a node as collapsed or expanded, provided they can be expanded on-click
:::