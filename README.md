# matrix2cleantax

Converter from matrix representation of Taxon Concept alignments to
CleanTax format, as used by
[EulerX](https://github.com/EulerProject/EulerX/).

## Prerequisites

 * GNU `gawk` (or other AWK). Make sure the ‘shebang’ points to your `gawk`.

## Usage

 1. Wrestle a spreadsheet format into a pipe-delimited (‘`|`’) matrix.
    Or just edit a plain text file to reflect the alignments. If a TC
    overlaps several Least Divisible Taxonomic Units (LDTU; a la Weakley), 
    enter the same label in each column.
 2. Run with `mx2ct in.csv > out.ct`
 3. Then (minimally) run: `euler2 align out.ct`, and `euler2 show pw`
 
 
