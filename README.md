# make_rep_database

program of detecting and clustering repeat sequences from reads.

## Description

`make_rep_database` detects and classifies the repeat sequences from reads in FASTA file, and outputs the repeat databases with FASTA format.

## Requirement

- seqkit Version: 0.8.0
- samtools Version: 1.7 Using htslib 1.7
- minialign Version: 0.6.0-42-g4d6b274, Build: SSE4.1

realignerとdump-consensusの設定は、DocBase参照。

- realigner commit-number: 1b80e94e8139b6fa710876044651bc17b0405d06

- dump-consensus commit-number: a7733b5e0d89c7536f72c3f4e1d5a0c7747d013f

- multialn  comimt-number: 8102e5be6e1319fb07917c44cb484f564ddd91ff

- haskell-sam   commit-number: e8d1bc609eae5415755ca3084b308dcba12d4d7d

- fastlinkedlist    commit-number: bac809b90ed06b2fbb28b78da7c69021e3641d53

- bioseq    commit-number: d36162340f88169a137797124e437e44a6e688ac

- attoparsec-applicative    comimt-number: bd4b2902570dec6af0078171b94075f25f01e708

- python3

    - pysam　Version: 0.11.2.2

    - wiggelen Version: 0.4.1

    - scipy Version: 1.0.1

    - matplotlib Version: 2.2.2

    - biopython Version: 1.71


## Usage

`make_rep_database.sh -in input.fa -d output_directory -re realigner_directory -du dump-consensus_directory -top the_number_of_top_reads_to_use -it the_maximum_number_of_iterations_of_realigner -cov threshold_of_depth -int threshold_of_peak_interval -pe threshold_of_peak_coverage -cut threshold_of_cut_interval`

今の仕様だと、`-in`の後に入力のFASTAファイルを書き、`-d`の後に出力ファイルを出すディレクトリを指定し、`-re`の後にrealignerのディレクトリを指定、`-du`の後にdump-consensusのディレクトリを指定、`-top`の後に長い順に上から何本をrepeat検出のreferenceとして使うかを指定、`-it`の後にrealignerを最大何回回すかを指定、`-cov`の後にカバレッジいくつ以上の領域をリピートとみなすかを指定、`-int`の後に何bp内のリードの終端のカバレッジを極大値とみなすかを指定、`-pe`の後にリードの終端の数がいくつ以上のとき、ピークとみなすかを指定、`-cut`の後にリピート領域の切断位置がそれぞれ何bp以上離れているかを指定する。(オプション多すぎるため、設定ファイルを用意したほうがよさそう。)

出力として、

## Installation

    $ git clone https://github.com/b4b4r07/awesome-tool

## Author

Taro Ozawa

## License