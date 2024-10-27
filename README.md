# eamena-data

EAMENA refrefence data, and curated datasets regularly published ([published data](https://github.com/eamena-project/eamena-data/tree/main/published-data)) into the ['eamena' community on Zenodo](https://zenodo.org/communities/eamena).

## Reference Data

### Concepts

Iconic images (i.e. visual documentation) of particular cases of Threats, Disturbances, etc., affecting Heritage Places are listed in [list.tsv](https://github.com/eamena-project/eamena-data/blob/main/reference-data/concepts/heritage_places/cases/list.tsv) and stored in the [img/](https://github.com/eamena-project/eamena-data/tree/main/reference-data/concepts/heritage_places/cases/img) folder, while the `concepts_images.ipynb` ([GitHub](https://github.com/eamena-project/eamena-data/blob/main/reference-data/concepts/heritage_places/concepts_images.ipynb) | [Colab](https://colab.research.google.com/github/eamena-project/eamena-data/blob/main/reference-data/concepts/heritage_places/concepts_images_graph.ipynb)) script allows to manage images and metadata

<center>

| field | description |
|----------|----------|
| label_parent    | parent node name (ie field)  |
| label    | concept name (ie value, or case) |
| image    | image filename   |
| uuid    | EAMENA UUID of this case (ie value, list: [concepts_readonly.tsv](https://github.com/eamena-project/eamena-arches-dev/blob/main/dbs/database.eamena/data/reference_data/concepts/concepts_readonly.tsv)) |
| uuid_parent    | EAMENA UUID of the parent node (ie field, list: [mds-template-readonly.tsv](https://github.com/eamena-project/eamena-arches-dev/blob/main/dbs/database.eamena/data/reference_data/rm/hp/mds/mds-template-readonly.tsv))  |

<em>The list.tsv table</em>

</center>

see: [eamena-arches-dev/.../reference_data#values](https://github.com/eamena-project/eamena-arches-dev/tree/main/dbs/database.eamena/data/reference_data#values)


