<!-- DO NOT EDIT! Automatically generated file. -->
# Data IO (Python functions)
[TOC]

A TFRecords file represents a sequence of (binary) strings.  The format is not
random access, so it is suitable for streaming large amounts of data but not
suitable if fast sharding or other non-sequential access is desired.

*   [`tf.python_io.TFRecordWriter`](../../api_docs/python/tf/python_io/TFRecordWriter.md)
*   [`tf.python_io.tf_record_iterator`](../../api_docs/python/tf/python_io/tf_record_iterator.md)
*   [`tf.python_io.TFRecordCompressionType`](../../api_docs/python/tf/python_io/TFRecordCompressionType.md)
*   [`tf.python_io.TFRecordOptions`](../../api_docs/python/tf/python_io/TFRecordOptions.md)

- - -

<h2 id="TFRecords_Format_Details">TFRecords Format Details</h2>

A TFRecords file contains a sequence of strings with CRC hashes.  Each record
has the format

    uint64 length
    uint32 masked_crc32_of_length
    byte   data[length]
    uint32 masked_crc32_of_data

and the records are concatenated together to produce the file.  The CRC32s
are [described here](https://en.wikipedia.org/wiki/Cyclic_redundancy_check),
and the mask of a CRC is

    masked_crc = ((crc >> 15) | (crc << 17)) + 0xa282ead8ul
