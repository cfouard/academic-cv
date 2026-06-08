---
title: Publications
type: landing
cms_exclude: true

sections:
  - block: collection
    id: journals
    content:
      title: International Peer-Reviewed Journals
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
      title: International Peer-Reviewed Conferences
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
      title: Patents
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
      title: Other (workshops, reports, etc.)
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