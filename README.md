PCR - Producer Consumer Ratio
=====
This script is a Bro implementation of the Producer-Consomer Ratio described by Carter Bullard and John Gerth at FloCon 2014.
Their presentation is located at : http://resources.sei.cmu.edu/asset_files/Presentation/2014_017_001_90063.pdf

Summary
---------
PCR is a metric designed to show the degree to which a network sessions payload is upstream or downstream for the purpose of data exfiltration detection.

PCR is a normalized value between -1 and 1 with negative values indicating consumption of data and positive values indicating production of data.

-1.0 Consumer <= PCR <= 1.0 Producer


Implementation
---------
This implementation of PCR provides two different metrics:

1. Every flow in the 'conn.log' is appended with a column called 'pcr' that indicates the PCR of the flow
2. All hosts in subnets defined in Site::local_nets have an average 'pcr' value calculated for them on a 1 minute interval


Future work
---------
* Calculate more than one PCR average - one for local networks and other for remote networks

