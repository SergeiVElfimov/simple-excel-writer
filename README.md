# Simple Excel Writer

[![build-status-image]][build-status]
[![codeql-image]][codeql]
[![pypi-version]][pypi]
[![pypi-downloads]][pypi]

Simple library to write excel files.

## Examples

```python
import xlsxwriter
from simple_excel_writer import SimpleExcelFileCreator

excel_header = ("Header 1", "Header 1")
excel_data = [["row 1 1", "row 1 2"], ["row 2 1", "row 2 2"]]
excel_sheetname: str = "Sheet 1"
excel_table_label: str | None = None
datetime_cell_format = {"num_format": "dd.mm.yyyy h:mm;@", "border": 1, "border_color": "#000000"}
date_cell_format = {"num_format": "dd.mm.yyyy", "border": 1, "border_color": "#000000"}
percent_cell_format = {"num_format": '0.00"%"', "border": 1, "border_color": "#000000"}
format_cell_border = {"border": 1, "border_color": "#000000", "text_wrap": True}
format_header_table = {"bold": True, "align": "center", "border": 1, "border_color": "#000000", "text_wrap": True}
table_label_format = {"italic": True, "font_size": 14}

excel_creator = SimpleExcelFileCreator(
    header=excel_header,
    data=excel_data,
    worksheet_label=excel_sheetname,
    table_label=excel_table_label,
    datetime_cell_format=datetime_cell_format,
    date_cell_format=date_cell_format,
    percent_cell_format=percent_cell_format,
    format_cell_border=format_cell_border,
    format_header_table=format_header_table,
    table_label_format=table_label_format,
)
excel_creator.get_excel_for_response()
```

## Required
- python >=3.10, <4.0
- pillow >=9.2
- xlsxwriter >=1.3.6
- pytz >=2020.1

## Installation
```pip install simple-excel-writer```


[build-status-image]: https://github.com/SergeiVElfimov/simple-excel-writer/actions/workflows/python-package.yml/badge.svg
[build-status]: https://github.com/SergeiVElfimov/simple-excel-writer/actions/workflows/python-package.yml
[codeql-image]: https://github.com/SergeiVElfimov/simple-excel-writer/actions/workflows/codeql.yml/badge.svg
[codeql]: https://github.com/SergeiVElfimov/simple-excel-writer/actions/workflows/codeql.yml
[pypi-version]: https://img.shields.io/pypi/v/simple-excel-writer.svg
[pypi-downloads]: https://img.shields.io/pypi/dm/simple-excel-writer?color=%232E73B2&logo=python&logoColor=%23F9D25F
[pypi]: https://pypi.org/project/simple-excel-writer/
