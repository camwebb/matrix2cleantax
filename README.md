# matrix2cleantax

Converter from matrix representation of Taxon Concept alignments to
CleanTax format, as used by
[EulerX](https://github.com/EulerProject/EulerX/).

## Prerequisites

 * GNU `gawk` (or other AWK). Make sure the ‘shebang’ points to your `gawk`.

## Input file coding

 * No header row. 
 * The first column should contain a code for the taxon concept system
   (e.g., a publication, or person), _aka_ Taxonomic Event.
 * Following columns indicate divisions of the encompassing taxon into
   Least Divisible Taxonomic Units (LDTUs; a la Weakley). A specimen
   will fall into one of these LDTUs, and theoretically be present in
   the same LDTU (column) for all rows.  Cells contain labels; the sum
   of all cells on a row with the same label indicates the extent of
   the taxon concept (TC). Labels will generally be the taxonomic name
   (or code for a name). Alignment between the full extent of a label
   between rows indicates the nature of the relationship between taxon
   concepts. See [example](example/test.csv).
 * Note that if a TC overlaps several LDTUs, enter the same label in
   each column; i.e., un-merge the cells in the spreadsheet.
   
## Usage

 1. Wrestle a spreadsheet format into a pipe-delimited (‘`|`’) matrix.
    Or just edit a plain text file to reflect the alignments. 
 2. Run with `mx2ct in.csv > out.ct`
 3. Then (minimally) run: `euler2 align out.ct`, and `euler2 show pw`
