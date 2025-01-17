## Cloud native file formats

List and describe the common properties of cloud native file formats like COG and ZARR.

### Data Chunks


### Pyramids


### WMS WMTS ?

Mention what this service enables (web viewers for example), connect to the previous pyramids topic.

Quiz about them: pyramids, chunks

### STAC Catalogs? (Or better in Data Discovery?)

### Compression

## Compression Quiz

Consider a cloud provider, that should decide if compressing the data on its storage would let it spare money.

If the compression process of a COG takes 0.05 CPU hour every 1 GB of data, the total amount of COGs on the storage takes 1200 TB and one CPU hour costs 0.05€ for the first 10000 CPU hour and then 0.03€ for the rest, how much would the compression process cost?

    [( )] 3000€
    [( )] 1200€
    [(X)] 2000€
    [( )] 2043€

Solution:
- 1 TB = 1000 GB following the international standard, see https://en.wikipedia.org/wiki/Gigabyte.
- The amount of data on the storage is 1200 TB * 1000 GB/TB = 1200000 GB
- If to compress 1 GB of data takes 0.05 CPU hour, to compress 1200000 GB it will take: 1200000 GB * 0.05 CPU hour / GB = 60000 CPU hour
- The first 10000 CPU hour cost 10000 CPU hour * 0.05 €/CPU hour = 500€
- The rest is 50000 CPU hour and it will cost 50000 CPU hour * 0.03 €/CPU hour = 1500 €
- The total is 500 € + 1500 € = 2000 €

In the same scenario, now we also consider the storage maintanance cost. If each TB of storage has a maintenance cost of 0.5 € every month, how much time would it take before the compression would let the cloud provider spare money? Consider a compression rate of 70%.

    [( )] ~ 9 months
    [( )] ~ 10 months
    [(X)] ~ 11 months
    [( )] ~ 12 months

Solution:
- Without compression, every month the storage would cost: 1200 TB * 0.5 €/TB = 600 €
- With a compression rate of 70%, the data would use 1200 TB * 0.7 = 840 TB of disk space
- With compression, every month the storage would cost: 840 TB * 0.5 €/TB = 420 €
- With compression, each month it's possible to spare 180 €.
- Since the compression process costs 2000 €, and each month costs 180 € less with it, it would take 2000 € / 180 €/month ~= 11 months to start to spare money.

### Video from VITO or SentinelHub/Sinergise/Planet:

Prepare some questions like:

- Is important to store the data in a compressed format?
- What is the role of data chunking in the overall back-end efficiency?

### openEO example on data access