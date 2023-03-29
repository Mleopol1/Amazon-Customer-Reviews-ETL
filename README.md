# Amazon Customer Reviews ETL

In this repository, ETL (Extract, Transform, and Load) is performed on two Amazon customer review datasets. The goal of this project is to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance.

## Datasets

Two datasets from [Amazon Reviews](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) are used:
* Amazon Video Games Reviews
  * Used in the "part_one_video_games.ipynb" file
* Amazon Musical Instruments Reviews
  * Used in the "part_one_musical_instruments.ipynb" file

## Extract

To begin, the datasets are imported using the correct `header` and `sep` parameters. The number of rows in each dataset is then counted.

## Transform

For each dataset, the schema.sql file located in the Resources folder is used to create the following four DataFrames:

   * `review_id_df` with the appropriate columns and data types.
   * `products_df` that drops the duplicates in the `product_id` and `product_title` columns.
   * `customers_df` that groups the data on the `customer_id` by the number of times a customer reviewed a product.
   * `vine_df` that has the `review_id`, `star_rating`, `helpful_votes`, `total_votes`, and `vine` columns.

## Load

Finally, each DataFrame is exported into the RDS instance to create four tables for each dataset.

## References
Amazon Customer Reviews Dataset. (n.d.). Retrieved April 08, 2021, from: [https://s3.amazonaws.com/amazon-reviews-pds/readme.html](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)
