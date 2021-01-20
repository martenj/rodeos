.. _impl_demux:

=========================
Connecting Demultiplexing
=========================

Demultiplexing is a data generation step similar to instruments that write data.
Data is read from Illumina sequencer run directories, possibly from the ``${LZ}-INGESTED`` "shadow" landing zone directory.
Usually, the ``bcl2fastq2`` tool by the vendor Illumina is run in a custom wrapper script.
The wrapper script should write a marker file indicating the completion of the demultiplexing process.

The RODEOS Ingest software comes with built-in support for our software package `Digestiflow <https://digestiflow-server.readthedocs.io/en/master/?badge=master>`__ but its implementation is generic and also allows custom demultiplexing scripts with custom marker file names.
