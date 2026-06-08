---
title: Publications
type: landing
cms_exclude: true

sections:
  - block: collection
    id: journals
    content:
      title: Revues internationales à comité de lecture
      count: 0
      filters:
        folders:
          - publication
        publication_type: 'article-journal'
      sort_by: Date
      sort_ascending: false
    design:
      view: citation
      columns: '1'

  - block: collection
    id: conferences
    content:
      title: Conférences internationales à comité de lecture
      count: 0
      filters:
        folders:
          - publication
        publication_type: 'paper-conference'
      sort_by: Date
      sort_ascending: false
    design:
      view: citation
      columns: '1'

  - block: collection
    id: patents
    content:
      title: Brevets
      count: 0
      filters:
        folders:
          - publication
        publication_type: 'patent'
      sort_by: Date
      sort_ascending: false
    design:
      view: citation
      columns: '1'

  - block: collection
    id: others
    content:
      title: Autres (workshops, rapports, etc.)
      count: 0
      filters:
        folders:
          - publication
        publication_type: 'report'
      sort_by: Date
      sort_ascending: false
    design:
      view: citation
      columns: '1'
---