go-xmp
===========

[![Build Status](https://travis-ci.org/echa/go-xmp.svg?branch=master)](https://travis-ci.org/echa/go-xmp)
[![GoDoc](https://godoc.org/github.com/echa/go-xmp?status.svg)](https://godoc.org/github.com/echa/go-xmp)


go-xmp is a native [Go](http://golang.org/) SDK for the [Extensible Metadata Platform](http://www.adobe.com/devnet/xmp.html) (XMP) as defined by the Adobe XMP Specification [Part 1](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/xmp/pdfs/XMP%20SDK%20Release%20cc-2016-08/XMPSpecificationPart1.pdf), [Part 2](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/xmp/pdfs/XMP%20SDK%20Release%20cc-2016-08/XMPSpecificationPart2.pdf) and [Part 3](http://wwwimages.adobe.com/content/dam/Adobe/en/devnet/xmp/pdfs/XMP%20SDK%20Release%20cc-2016-08/XMPSpecificationPart3.pdf), a.k.a ISO 16684-1:2011(E).

Features
--------

### Included metadata models

* XMP DublinCore (dc)
* XMP Media Management (xmpMM)
* XMP Dynamic Media (xmpDM)
* XMP Rights (xmpRights)
* XMP Jobs (xmpBJ)
* XMP Paged Text (xmpTPg)
* EXIF v2.3.1 (exif, exifEX)
* Adobe Camera Raw (crs)
* Creative Commons (cc)
* DJI Drones (dji)
* ID3 v2.2, v2.3, v2.4 (id3)
* iXML audio recorder (ixml)
* iTunes/MP4 (itunes)
* ISO/MP4 (mp4)
* Quicktime (qt)
* PhotoMechanic (pm)
* Tiff (tiff)
* Riff (riff)
* Photoshop (ps)
* PDF (pdf)

### Metadata models available under commercial license

* ACES Image Metadata
* AEScart
* ARRI Camera Metadata
* ASC CDL
* EBU Broadcast WAV
* Getty Images
* IPTC Core 1.2, IPTC Extension 1.3, IPTC Video Metadata 1.0
* Plus Licensing Metadata
* SMPTE DPX Image Metadata
* SMPTE MXF Metadata
* OpenEXR Image Header Metadata
* XMP Media Production SDK (Universal Metadata Container)


Documentation
-------------

- [API Reference](http://godoc.org/github.com/echa/go-xmp)
- [FAQ](https://github.com/echa/go-xmp/wiki/FAQ)

Installation
------------

Install go-xmp using the "go get" command:

    go get github.com/echa/go-xmp

The Go distribution is go-xmp's only dependency.

Examples
--------




Benchmarks
----------

```
  Compression Results 421        mean               min                  max
  -----------------------------------------------------------------------------
        Original sizes       4082 (100.0)        820 (100.0)      86940 (100.0)
             XMP sizes       3053 ( 74.1)        681 ( 38.9)      75337 (113.4)
        XMP Gzip sizes       1030 ( 27.2)        369 (  7.6)       7866 ( 51.5)
      XMP Snappy sizes       1430 ( 37.2)        456 ( 11.6)      12967 ( 68.7)
            JSON sizes       1852 ( 43.0)        306 ( 18.5)      62824 ( 90.3)
       JSON Gzip sizes        782 ( 20.3)        209 (  5.3)       7566 ( 49.5)
     JSON Snappy sizes       1099 ( 28.0)        252 (  7.8)      11763 ( 77.0)
  -----------------------------------------------------------------------------
        XML->XMP times          348.609µs            73.19µs         5.156559ms
       XMP->JSON times          194.575µs           34.239µs         4.500886ms
        XMP->XML times          200.663µs           35.576µs         3.771858ms
        XMP Gzip times          242.649µs           99.493µs         1.656697ms
      XMP Snappy times           25.241µs           10.101µs          261.962µs
       JSON Gzip times          210.843µs           88.285µs          817.533µs
     JSON Snappy times           26.084µs            9.305µs          161.167µs
```

XMP Marshal Benchmark using `premiere-cc.xmp`, a rather large xmpDM file with history, xmpMM:Pantry etc.

```
BenchmarkUnmarshalXMP-8         5000      339876 ns/op     56827 B/op     1007 allocs/op
BenchmarkMarshalXMP-8           5000      257008 ns/op     60776 B/op      773 allocs/op
BenchmarkMarshalJSON-8          5000      354320 ns/op     89390 B/op     1099 allocs/op
BenchmarkUnmarshalJSON-8        5000      334702 ns/op     55558 B/op      915 allocs/op
```

Contributing
------------

See [CONTRIBUTING.md](https://github.com/echa/go-xmp/blob/master/.github/CONTRIBUTING.md).


License
-------

go-xmp is available under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).
